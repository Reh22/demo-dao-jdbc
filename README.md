# Projeto: demo-dao-jdbc
#### Sumário
* [Introdução](#introdução)
  - [Objetivo](#objetivo)
  - [Evolução](#evolução)
* [Equipe](#equipe)
* [Descrição Funcional](#descrição-funcional)
* [Descrição Técnica](#descrição-técnica)
  - [Pré-requisitos](#pré-requisitos)
  - [Detalhes Técnicos](#detalhes-técnicos)
  - [Compilação](#compilação)
  - [Execução da Aplicação](#execução-da-aplicação)
  - [Funcionalidades desta aplicação](#funcionalidades-desta-aplicação)


## Introdução
Migração da aplicação em Visual Basic -  SACPAM01

## Objetivo
Migrar a aplicação em Visual Basic -  SACPAM01 para Java - JAB3

## Evolução
| Início | Término |
| ------- | -------- |
| 01/22 | 09/22 |

## Equipe
| Cargo | Nome | Email |
| ------ | ----- | ------ |
| Desenvolvedor		 | Renato dos Santos       | renatorenatex20@gmail.com   |


## Descrição Funcional
resumo da historia do projeto
requisitos funcionais

## Descrição Técnica
### Pré-requisitos
| Componente   | Versão       | Descrição                      |
|--------------|--------------|--------------------------------|
| OpenJDK      | 17.0.3.1       | 17.0.3.1" 2022-04-22 LTS |

### Detalhes Técnicos
| Requisito |  |
| ------ | ------ |


  
  

![Sequencia PAM](./pam.png)

### Compilação
Para fazer o download de dependências e fazer o `Build` da aplicação.
em _run configurations_ no campo `Goals`
```bash
clean install package
```
### Execução da Aplicação
Para executar a aplicação em modo de desenvolvimento, ative o _profile_ `hml`. 
Em _run configurations_ nas configuraçãoes da aplicação: 
Na guia `Arguments` com os parâmetros: 
- arquivo do resultado
- caminho do aquivo
- funcionalidade para executar -  `código da funcionalidade` ou `TODOS`
- 0
- data inicial
- data final
```bash
C:/opt/connect/pam/saida/arquivoRetorno.txt
C:/opt/connect/pam/saida/
DEV_TEST
0
2020-12-21
2021-01-21
```
Na guia `VM Arguments` os parâmetros: 
- runninMode -  `HML` ou `PROD`
- pamDir -  Diretorio onde está rodando a aplicação -  `será usado para mapear os diretórios dos arquivos de login na base de dados (cacert | pem)`
```bash
-DrunningMode=hml
-DpamDir=Diretorio da aplicação
-DrestModeRead=false
-DrestModeWrite=false
```
## Funcionalidades desta aplicação
| Código | Nome | Descrição                      |
| ----- | ----- | ---------                      |
| AMORT_DIV   | importarCargaAmortizacaoDividendos  | Deleta dados na tabela TB_RENT_DIVD_AMTZ e, após, insere dados na tabela TB_RENT_DIVD_AMTZ |
