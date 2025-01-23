# Configurações


## Verificador de Pull Requests (Azure)
* Para utilizar o validador é necessario a criação do Token de acesso;
* As premissões devem ser apenas de leitura (URLBASE/_usersSettings/tokens)
* O arquivo .env deve conter as seguintes tags
    
```sh
        URLBASE=https://empresa.azure.com
        ORGANIZATIONID=eabf52e-aef4d-99eda-abb4-3410d184274d
        TOKEN=1234567890
        MINREVIEWPR=4
        ALERTPRCOMPLET=True|False
        
```

URLBASE: Url base do repositorio

ORGANIZATIONID: ID da organização

TOKEN: token de acesso gerado no Azure

MINREVIEWPR: Numero minimo de PRs realizados para que seja gerado um alerta de pronto

ALERTPRCOMPLET: se você deseja que o App te avise quando o numero minmo de PRs forem realizados


# Regras de Funcionamento
## Você como Revisor
* A cada 30 minutos será consutado se há PR´s que foram indicados a você e que você não tenha votado para que seja exibido um alerta em sua tela para que este PR seja avalidado. 
* Independente do numero de PRs realizados para seu parceiro será emitido um alerta em sua tela caso você não tenha realizado sua verificação.
* Caso decline ou vote no PR de seu parceiro, o alerta não será mais emitido.

## Você como Solicitante
* Quando você solicitar um PR ao time, e estiver com o ALERTPRCOMPLET como verdadeiro e houver o minimo de PRS realizados com aprocação, será emitido um alerta para que você finalize o seu PR
* Quando um parceiro no qual você soliticou o PR,  negue ou esteja aguardando sua revisão, também será emitido um alerta em sua tela para que seja verificado seu PR.
* Sempre que um alerta for emitido, será necessario escolher abrir ou apenas passar o PR a analisar.

