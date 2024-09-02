organizador_planilha
Sumário

    Introdução
    Instalação
    Uso Básico
    Funções Disponíveis
    Interface Gráfica
    Exemplo de Uso
    Contribuição
    Licença

Introdução

O organizador_planilha é uma ferramenta prática para realizar consultas em bancos de dados MySQL e exportar os resultados para uma planilha Excel. Além disso, ele oferece funcionalidades para sanitizar nomes de colunas e dados, e organizar planilhas com base em uma coluna específica.
Instalação

Para instalar o organizador_planilha, execute:

bash

pip install organizador_planilha

Uso Básico
Importando o Pacote

python

from organizador_planilha import buscar_planilha, organizar_planilha

1. buscar_planilha(query, banco, servidor, senha, usuario, nome_planilha)

Executa uma consulta SQL no banco de dados especificado e exporta os resultados para uma planilha Excel.
Parâmetros:

    query (str): A consulta SQL a ser executada.
    banco (str): O nome do banco de dados.
    servidor (str): O endereço do servidor MySQL.
    senha (str): A senha para acessar o banco de dados.
    usuario (str): O nome do usuário do banco de dados.
    nome_planilha (str): O nome do arquivo Excel a ser gerado (sem extensão).

Exemplo de Uso:

python

buscar_planilha(
    query="SELECT * FROM minha_tabela",
    banco="meu_banco",
    servidor="localhost",
    senha="minha_senha",
    usuario="meu_usuario",
    nome_planilha="resultado_consulta"
)

2. organizar_planilha(input_path, output_path, coluna_ordenar)

Organiza uma planilha (em formato .csv ou .xlsx) com base em uma coluna específica e salva o resultado em um novo arquivo.
Parâmetros:

    input_path (str): Caminho para a planilha de entrada.
    output_path (str): Caminho para salvar a planilha organizada.
    coluna_ordenar (str): Nome da coluna pela qual a planilha deve ser organizada.

Exemplo de Uso:

python

organizar_planilha(
    input_path="dados.csv",
    output_path="dados_organizados.xlsx",
    coluna_ordenar="nome"
)

Interface Gráfica

O pacote também fornece uma interface gráfica para facilitar a interação com o usuário. Esta interface permite inserir os parâmetros da consulta SQL e executar o processo de forma interativa.
Iniciando a Interface Gráfica

Para iniciar a interface gráfica, use:

python

from organizador_planilha import gui

gui.run()

Exemplo de Uso
Script Completo

python

from organizador_planilha import buscar_planilha, organizar_planilha

# Executando uma consulta e gerando uma planilha Excel
buscar_planilha(
    query="SELECT * FROM minha_tabela",
    banco="meu_banco",
    servidor="localhost",
    senha="minha_senha",
    usuario="meu_usuario",
    nome_planilha="resultado_consulta"
)

# Organizando a planilha gerada com base na coluna 'nome'
organizar_planilha(
    input_path="resultado_consulta.xlsx",
    output_path="resultado_organizado.xlsx",
    coluna_ordenar="nome"
)

Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests no repositório do GitHub. Ao contribuir, siga as melhores práticas de codificação e inclua testes para suas mudanças.