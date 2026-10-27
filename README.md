# Sistema de Gestão de Estoque

Duas interfaces (desktop e web) sobre o mesmo núcleo e o mesmo arquivo `estoque.json`.

## Arquivos
- `estoque_core.py`: dados (lista de dicionários), persistência JSON, validação com try/except e as funções do sistema
- `app_desktop.py`: versão desktop em Tkinter (layout responsivo)
- `app_web.py`: versão web em Flask (responsiva, tabela vira cartões no celular)

## Como executar
Desktop (só precisa do Python 3.9+; o Tkinter já vem com ele):

    python app_desktop.py

Web:

    pip install flask
    python app_web.py

Abra http://127.0.0.1:5000. Para acessar do celular, use o IP do computador na mesma rede (porta 5000).

## Funções próprias (estoque_core.py)
`carregar_dados`, `salvar_dados`, `validar_campos`, `gerar_id`, `encontrar_produto`,
`adicionar_produto`, `editar_produto`, `remover_produto`, `movimentar_estoque`,
`situacao`, `buscar_produtos`, `calcular_resumo`, `formatar_moeda`.

## Recursos
- Cadastro, edição, exclusão e busca de produtos
- Entrada e saída de estoque (a saída não pode passar do saldo)
- Alerta de estoque baixo/esgotado (linhas coloridas)
- Cartões de resumo: produtos, itens, valor em estoque e alertas
- Validação: nome obrigatório, quantidade inteira, preço numérico (aceita vírgula), sem duplicados
- Gravação segura do JSON (arquivo temporário + troca) e proteção contra arquivo corrompido

## Responsividade
- Desktop: abaixo de 900 px de largura o formulário passa para cima da tabela
- Web: grade fluida, formulário empilha em telas estreitas e a tabela vira cartões abaixo de 700 px; tema escuro automático
