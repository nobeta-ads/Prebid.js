# Build para o script nobeta

## Atualizar projeto via github
Antes de começar, sincronize o fork do repositório original em https://github.com/nobeta-ads/Prebid.js, clicando em "Sync fork"
```
git pull origin master
```

## Atualizar para versão estável

No arquivo package.json, trocar a versão para uma versão estável, verificando entre os commits, qual é o último realese e fazer o checkout
```
npm update
```

## Adapters
- AdPone
- AppNexus
- RTBHouse
- Smart Adserver
- SeedTag
- Smile Wanted - adicionado em 07/11/24

## Módulos
- Supply Chain Object ( schain)
- Demand Chain Object ( dchain )
- Currency ( currency )
- Fledge (PAAPI) for GPT ~~( fledgeForGpt )~~ ( paapiForGpt )

## Módulos Padrões
- ~~Consent Management - GDPR ( consentManagement )~~ Não disponivel
- Consent Management - GPP ( consentManagementGpp )
- Consent Management - US Privacy ( consentManagementUsp )

## Object Global Name

Caso seja nsecessário, alterar o valor "globalVarName" no arquivo package.json. Atualmente como pbjs_nobeta para a tag nova e pbjs para a tag antiga. Só siga este passo se **A implementação também conste o mesmo nome definido como Global Name.


## Build

```
gulp build --modules=consentManagementGpp,consentManagementUsp,adponeBidAdapter,appnexusBidAdapter,rtbhouseBidAdapter,smartadserverBidAdapter,seedtagBidAdapter,smilewantedBidAdapter,currency,schain,dchain,paapiForGpt
```

## Saída do arquivo
O arquivo compilado é gravado no arquivo **build/dist/prebid.js**
```
cp build/dist/prebid.js ../exemplo/app/admanager_assets/
```

## Publicação
Usar o playbook para subir e atualizar os projetos dependentes: https://docs.google.com/document/d/1G9h-5Sge3Hz3MwsZtH4OJgk_6itrbfsj5Kq6KNmLUhk/edit?tab=t.0

## Criação do criativo no admanager
https://admanager.google.com/150684666#creatives/creative/list/view=standard

