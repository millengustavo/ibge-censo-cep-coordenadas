# IBGE - Censo 2010 - Localização para Código de Setor Censitário

Repositório com código utilizado para criação da base hospedada no Kaggle: [https://www.kaggle.com/silveiragustavo/ibge-censo-cep-coordenadas-renda-per-capita](https://www.kaggle.com/silveiragustavo/ibge-censo-cep-coordenadas-renda-per-capita)

## Contexto

Os dados do censo 2010 do IBGE são muito ricos, mas há sempre um grande trabalho a ser feito para consolidar as informações. O código de setor censitário permite associar a determinados locais muitos indicadores sociais importantes, como a renda per capita aproximada. 

A base Open Addresses South America traz um bom compilado de código postal (CEP) e coordenadas geográficas (latitude e longitude). Os shape files (.shp) provenientes do IBGE permitem associar o código de setor censitário a um polígono de coordenadas geográficas.

Da base Open Addresses aproximamos um CEP para somente um ponto de coordenadas utilizando a mediana. Utilizando geopandas, conseguimos associar o ponto de cada CEP a um polígono de setor censitário, resultando numa base com CEP, coordenadas e código de setor censitário. Essa base por si só é um ponto de associação de localização, seja por CEP ou coordenadas geográficas, com indicadores socioeconômicos provenientes do censo 2010 utilizando o código de setor censitário como chave.

Como um exemplo de aplicação, utilizando os dados dos arquivos PessoaRenda_UF, calculamos a renda per capita aproximada por setor censitário.


## Conteúdo

O arquivo `census_code_cep_coordinates.csv` contém informações de CEP, a mediana de suas coordenadas (latitude e longitude) e o código de setor censitário do censo de 2010 do IBGE.

O arquivo `cep_coordinates_per_capita_income.csv` associa as informações do arquivo acima com a informação de renda per capita aproximada proveniente dos arquivos de PessoaRenda_UF, mais especificamente das colunas:
- V020: Pessoas de 10 anos ou mais de idade com ou sem rendimento
- V022: Total do rendimento nominal mensal das pessoas de 10 anos ou mais de idade

## Bases originárias
- SHP files dos setores censitários: [https://geoftp.ibge.gov.br/organizacao_do_territorio/malhas_territoriais/malhas_de_setores_censitarios__divisoes_intramunicipais/censo_2010/setores_censitarios_shp/](https://geoftp.ibge.gov.br/organizacao_do_territorio/malhas_territoriais/malhas_de_setores_censitarios__divisoes_intramunicipais/censo_2010/setores_censitarios_shp/)
- Agregados por setores censitários:
[https://ftp.ibge.gov.br/Censos/Censo_Demografico_2010/Resultados_do_Universo/Agregados_por_Setores_Censitarios/](https://ftp.ibge.gov.br/Censos/Censo_Demografico_2010/Resultados_do_Universo/Agregados_por_Setores_Censitarios/)
- Open Addresses South America:
[https://www.kaggle.com/openaddresses/openaddresses-south-america?select=brazil.csv](https://www.kaggle.com/openaddresses/openaddresses-south-america?select=brazil.csv)