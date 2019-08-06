# Documentação para a Importação de Anúncios da OLX Brasil

A OLX hoje suporta dois tipos de importação de anúncios, para anunciantes que querem gerenciar seus anúncios a partir de um software terceiro (ou seja, sem passar pelas interfaces nativas da OLX para gestão de inventário).

Há duas formas principais para integrar anúncios: via API ou via arquivo (JSON ou XML).

## Integração via arquivo (JSON ou XML)

Para a integração via Arquivo, a OLX vai consultar periodicamente (mínimo de uma vez por dia) o arquivo disponibilizado pelo anunciante. Para isso, caberá ao anunciante (junto com seu integrador, quando isso for aplicável) disponibilizar uma URL onde esse arquivo estará sempre disponível.

[Categoria Imóveis, via arquivo (XML)](https://github.com/olxbr/ad_integration/blob/master/docs/real_estate_xml.md)<br>
[Categoria Veículos, via arquivo (JSON)](https://github.com/olxbr/ad_integration/blob/master/docs/autos_json.md)<br>
[Categoria Autopeças, via arquivo (JSON)](https://github.com/olxbr/ad_integration/blob/master/docs/autoparts_json.md)

#### Inferência de Inserção

A OLX funciona com um modelo de inserção paga de anúncios. Para a importação de anúncios via arquivo, a OLX vai inferir que há uma nova inserção quando houver um `id` inédito no arquivo. Se um anúncio com um `id` já existente estiver no arquivo, presumiremos que é o mesmo anúncio e, no máximo, trataremos a operação como uma `edição` (e não `inserção`) caso hajam alterações nas informações do arquivo.


## Integração via API

Atualmente a OLX tem uma API para integração, que suporta apenas as categorias `Imóveis`, `Carros, vans e utilitários` e `Motos`. Uma nova versão está em desenvolvimento e será publicada aqui assim que disponível.

Para ter informações sobre a integração via API atual (chamada de Autoupload), contate suporteintegrador@olxbr.com.


