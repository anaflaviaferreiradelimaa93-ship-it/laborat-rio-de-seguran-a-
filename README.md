## ForenseWAF — Projeto Integrado em Perícia Computacional

## Sobre o projeto

O ForenseWAF é um laboratório de segurança web desenvolvido na disciplina de Perícia Computacional. O projeto demonstra a atuação de um Web Application Firewall (WAF) na identificação e no bloqueio de tentativas de ataques contra aplicações web, além da importância dos registros para a análise de incidentes digitais.

## Objetivo

Desenvolver um ambiente de testes para demonstrar a diferença entre o acesso direto a uma aplicação web e o acesso protegido por um WAF, utilizando uma tentativa de SQL Injection.

## Tecnologias utilizadas

- **Docker Desktop:** execução dos contêineres.
- **Ubuntu (WSL2):** ambiente Linux para execução de comandos e configuração.
- **Visual Studio Code:** edição e desenvolvimento dos arquivos.
- **OWASP Juice Shop:** aplicação utilizada nos testes.
- **ModSecurity:** ferramenta de proteção WAF.
- **OWASP Core Rule Set (CRS):** conjunto de regras de segurança.
- **Python:** desenvolvimento da API de monitoramento.
- **HTML, CSS e JavaScript:** desenvolvimento da interface visual.
- **cURL:** execução dos testes.

## Funcionamento do laboratório

O ambiente possui duas formas de acesso:

- **Porta 3000:** acesso direto ao OWASP Juice Shop.
- **Porta 8080:** acesso à aplicação passando pelo WAF.

Uma API desenvolvida em Python recebe os códigos HTTP informados pelos testes e atualiza o monitoramento visual. Os registros do ModSecurity são consultados separadamente para identificar as regras acionadas.

## Testes realizados

Foi simulada uma tentativa de SQL Injection nos dois cenários:

- **Acesso direto:** retorno HTTP 500, indicando erro no processamento da requisição pela aplicação.
- **Acesso pelo WAF:** retorno HTTP 403, indicando bloqueio da requisição.

Nos registros do ModSecurity, foram identificadas as regras 942100 e 949110 durante o teste protegido.

## Resultados

Os testes demonstraram o bloqueio da tentativa específica de SQL Injection pelo WAF e o funcionamento do monitoramento visual. Os registros também permitiram identificar a regra responsável pela detecção e pelo bloqueio.


## Evidências dos testes

### 1. Acesso direto à aplicação

Resultado do teste realizado sem a proteção do WAF.

![Teste direto](Captura de tela_10-11-2026_204935_localhost)

### 2. Acesso protegido pelo WAF

Resultado do teste realizado passando pelo ModSecurity.

![Teste com WAF](Captura de tela_10-11-2026_204850_localhost)

