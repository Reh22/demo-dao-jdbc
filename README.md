# demo-dao-jdbc

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
| GER		 | Daniel Ito de Souza       | dan.souza@f1rst.com.br   |
| PO		 | Emilene Fabiane Lourenco  | elourenco@f1rst.com.br   |
| SM		 | Ariane Cristina Rodrigues | ariane.rodrigues@f1rst.com.br    |
| DEV BACK   | Antonio Carlos da Silva   | antosilva@prservicos.com.br |
| DEV BACK   | Wendell Gomes Silva       | wendell.silva@prservicos.com.br |
| DEV BACK   | Everton Lima              | p000e_lima@prservicos.com.br    |
| QA         | Kaue Teixeira Santos      | kaue.santos@prservicos.com.br |

## Descrição Funcional
resumo da historia do projeto
requisitos funcionais

## Descrição Técnica
### Pré-requisitos
| Componente   | Versão       | Descrição                      |
|--------------|--------------|--------------------------------|
| OpenJDK      | 11.0.5       | java-11-openjdk-11.0.5.10-2.windows.redhat.x86_64 |
| Apache Maven | 3.6.1        | Build e Gestão de Dependências |

### Detalhes Técnicos
| Requisito |  |
| ------ | ------ |
| CloudBees | https://cloudbees.santanderbr.corp/gestao-controle/job/PAM/job/IAAS_PACOTES/job/PIPELINE-IAAS-IAAS_PACOTES-PAM/ |
| Cerberon | RP034956 |
| Banco de dados HML(Oracle)  | 'oraho108' |  

  
  

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
| XMLINTRA    | atualizaXMLIntranet  | |
| XMLINTLIE   | atualizaXMLIntraLIE  | |
| GERACSV     | geracaoCSVMatriz  | |
| ATUPRDSAC   | atualizaProduto  | Insere ou atualiza dados na tabela PAM_PRODUTO_ASSET_MANAGEMENT |
| CADSETOR    | carregaCadastroSetor  | Insere ou atualiza dados na tabela PAM_SETOR_ECONOMICO_SAC |
| CADEMISSOR  | carregaCadastroEmissor  | Chama a APi do Caceis [instituicaoFinanceira e empresa], <br>com o resultado chama a procedure PAMP_ITEMP_INSUPD Insere ou atualiza dados na tabela PAM_INSTITUICAO_EMISSORA_SAC<br>Esta function carregara para dentro do PAM os emissores de papel do sistema YMF |
| CADINE      | carregaCadastroIndicador  | Insere ou atualiza dados na tabela PAM_INE_FNRO_SAC |
| CADCARTR    | carregaCarteira  | Insere ou atualiza dados na tabela PAM_CARTEIRA_SAC |
| CADFERIADO  | carregaCadastroFeriado  | Deleta dados na tabela PAM_FERIADO_SAC e, após, insere dados na tabela PAM_FERIADO_SAC |
| ATUREGUA    | atualizaReguaDU  | Deleta e insere dados na tabela PAM_FERIADO_PAM e, após, insere ou atualiza dados na tabela PAM_REGUA_DIA_UTIL |
| COTINE      | carregaCotacaoIndicador  | Insere ou atualiza dados na tabela PAM_COTAC_INE_FNRO_SAC |
| ACUMINE     | atualizaCotac  | |
| POCARTR     | carregaPosicaoCarteira  | Insere ou atualiza dados na tabela PAM_POSICAO_CARTEIRA_SAC |
| ACUMRENTB   | atualizaRentab  | |
| ATUPARAMD0  | atualizaParametro  | |
| ACUMPRORATA | atualizaProRataMensal  | Insere dados na tabela PAM_COTAC_INE_FNRO_TMP e, após, insere ou atualiza dados na tabela PAM_RENTB_ACUM_PRO_BENCH |
| GESTORES    | atualizaPosicaoGestores  | |
| COMPRF      | carregaComposicaoRFPAM  | Deleta dados na tabela PAM_COMPSC_PRO_PAPEL, deleta dados na tabela PAM_CARTEIRA_RENDA_FIXA_SAC e, após, insere dados na tabela PAM_COMPSC_PRO_PAPEL e insere dados na tabela PAM_CARTEIRA_RENDA_FIXA_SAC |
| COMPRV      | carregaComposicaoRVPAM  | Deleta dados na tabela PAM_COMPSC_PRO_PAPEL, deleta dados na tabela PAM_CARTEIRA_RENDAVARIAVEL_SAC e, após, insere dados na tabela PAM_COMPSC_PRO_PAPEL e insere dados na tabela PAM_CARTEIRA_RENDAVARIAVEL_SAC |
| COMPFN      | carregaComposicaoFundosPAM  | Deleta dados na tabela PAM_COMPSC_PRO_PAPEL, deleta dados na tabela PAM_CARTEIRA_FUNDO_SAC e, após, insere dados na tabela PAM_COMPSC_PRO_PAPEL e insere dados na tabela PAM_CARTEIRA_FUNDO_SAC |
| COMPFU      | carregaComposicaoFuturoPAM  | Deleta dados na tabela PAM_COMPSC_PRO_PAPEL, deleta dados na tabela PAM_CARTEIRA_FUTURO_SAC e, após, insere dados na tabela PAM_COMPSC_PRO_PAPEL e insere dados na tabela PAM_CARTEIRA_FUTURO_SAC |
| COMPCX      | carregaComposicaoCaixaPAM  | Deleta dados na tabela PAM_COMPSC_PRO_PAPEL, deleta dados na tabela PAM_CARTEIRA_CAIXA_SAC e, após, insere dados na tabela PAM_COMPSC_PRO_PAPEL e insere dados na tabela PAM_CARTEIRA_CAIXA_SAC |
| COMPSW      | carregaComposicaoSwapPAM  | Deleta dados na tabela PAM_COMPSC_PRO_PAPEL, deleta dados na tabela PAM_CARTEIRA_SWAP_SAC e, após, insere dados na tabela PAM_COMPSC_PRO_PAPEL e insere dados na tabela PAM_CARTEIRA_SWAP_SAC |
| MVTOFN      | carregaComposicaoD0Fundos  | Insere ou atualiza dados na tabela PAM_CARTEIRA_FUNDO_SAC |
| ARQPRIV     | geraArquivosIndicesPrivate  | |
| ATUCTAFN    | atualizaCotasLiquidacao  | |
| TERMOMX     | gerarArquivoTermoMX  | |
| CADCVM  | carregaScriptASS  | Não migrado |
