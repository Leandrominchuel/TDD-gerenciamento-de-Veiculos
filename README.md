# TDD-gerenciamento-de-Veiculos
Sugestãoe de testes com codigo para o Sistema



Testes para Adicionar Cliente:

Teste de Adicionar Cliente com Dados Válidos:
     
     @Test
    public void testAdicionarClienteComDadosValidos() {
    GerenciamentoVeiculos gerenciamento = new GerenciamentoVeiculos();
    boolean resultado = gerenciamento.adicionarCliente("João", "Silva", "12345", "12345678901", "Rua A, 123");
    assertTrue(resultado);
}

Testes para Adicionar Veículo:
 Teste de Adicionar Veículo Novo:
 
    @Test
    public void testAdicionarVeiculoNovo() {
    GerenciamentoVeiculos gerenciamento = new GerenciamentoVeiculos();
    boolean resultado = gerenciamento.adicionarVeiculo("Automóvel", "VW", "NOVO", "POPULAR", 25000.0, "ABC-1234", 2023);
    assertTrue(resultado);
}

Teste de Adicionar Veículo com Dados Inválidos:

    @Test
    public void testAdicionarVeiculoComDadosInvalidos() {
    GerenciamentoVeiculos gerenciamento = new GerenciamentoVeiculos();
    boolean resultado = gerenciamento.adicionarVeiculo("Motocicleta", "Yamaha", "LOCADO", "INTERMEDIARIO", -1000.0, "XYZ-9876", 1990);
    assertFalse(resultado);
}

Teste de Adicionar Veículo com Marca Inválida:

    @Test
    public void testAdicionarVeiculoComMarcaInvalida() {
    GerenciamentoVeiculos gerenciamento = new GerenciamentoVeiculos();
    boolean resultado = gerenciamento.adicionarVeiculo("Van", "MarcaDesconhecida", "DISPONIVEL", "LUXO", 40000.0, "XYZ-1234", 2022);
    assertFalse(resultado);
}

Testes para Locação de Veículos:

    Teste de Locação Válida:

    @Test
    public void testLocacaoValida() {
    GerenciamentoVeiculos gerenciamento = new GerenciamentoVeiculos();
    boolean resultado = gerenciamento.locarVeiculo("ABC-1234", 5, dataLocacao, cliente);
    assertTrue(resultado);
}

Teste de Locação de Veículo Indisponível:

    @Test
    public void testLocacaoVeiculoIndisponivel() {
    GerenciamentoVeiculos gerenciamento = new GerenciamentoVeiculos();
    boolean resultado = gerenciamento.locarVeiculo("XYZ-9876", 3, dataLocacao, cliente);
    assertFalse(resultado);
}

Testes para Devolução de Veículos:

    Teste de Devolução de Veículo:

    @Test
    public void testDevolucaoVeiculo() {
    GerenciamentoVeiculos gerenciamento = new GerenciamentoVeiculos();
    gerenciamento.locarVeiculo("ABC-1234", 7, dataLocacao, cliente);
    boolean resultado = gerenciamento.devolverVeiculo("ABC-1234");
    assertTrue(resultado);
}

Teste de Devolução de Veículo Não Locado:

    @Test
    public void testDevolucaoVeiculoNaoLocado() {
    GerenciamentoVeiculos gerenciamento = new GerenciamentoVeiculos();
    boolean resultado = gerenciamento.devolverVeiculo("XYZ-9876");
    assertFalse(resultado);
}

Teste de Venda de Veículo:

    @Test
    public void testVendaVeiculo() {
    GerenciamentoVeiculos gerenciamento = new GerenciamentoVeiculos();
    boolean resultado = gerenciamento.venderVeiculo("ABC-1234");
    assertTrue(resultado);
}

Teste de Venda de Veículo Não Disponível para Venda:

    @Test
    public void testVendaVeiculoNaoDisponivel() {
    GerenciamentoVeiculos gerenciamento = new GerenciamentoVeiculos();
    boolean resultado = gerenciamento.venderVeiculo("XYZ-9876");
    assertFalse(resultado);
}



