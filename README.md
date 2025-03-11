Os deslizamentos de terra muitas vezes são responsáveis por provocar perda de vidas humanas, além de danos significativos à vida selvagem, ao gado e à topografia da região.  

Por isso, o objetivo deste script é utilizar imagens do satélite Sentinel-2 para avaliar a perda de vegetação causada por esses deslizamentos.  

Para conseguir isso, usaremos o **Índice de Vegetação de Diferença Normalizada (NDVI)**, uma métrica amplamente usada para avaliar a saúde e a densidade da vegetação. 

O NDVI usa a diferença entre as bandas vermelha e infravermelha próxima (NIR) para gerar um único valor representativo, tornando-o uma ferramenta poderosa para detectar mudanças na vegetação ao longo do tempo.

![image](https://github.com/user-attachments/assets/e667b304-1eb6-4851-b409-1f5b9bc6d9bd)

Esta análise demonstra como imagens de satélite podem fornecer insights acionáveis ​​sobre o impacto de desastres naturais. Neste caso, ela destaca a extensão da perda de vegetação, o que pode informar esforços de reflorestamento, planos de restauração ecológica e futuras estratégias de mitigação de desastres.

## Cadastro no site da Copernicus
Para iniciar as análises no script diff_ndvi_landslides.ipynb, crie um login no site abaixo. Utilizaremos o site da Copernicus para obter as imagens do Sentinel-2: 

https://dataspace.copernicus.eu/

## Autenticação 
No trecho do script que segue abaixo, é necessário entrar no link para autenticar seu acesso. Basta inserir login e senha e aceitar os termos:  

![image](https://github.com/user-attachments/assets/9a236899-ac49-4132-b574-5b8d9c0cc2c7)


## Região de estudo

A sua região de estudo precisa ser primeiramente definida no QGIS, ou qualquer outra ferramenta em que você possa selecionar a área de interesse e exporta-la como GeoJSON. Abaixo, demonstro o passo a passo para fazer isso no QGIS: 

### Passo 1 - Crie uma nova camada Shapefile

![image](https://github.com/user-attachments/assets/49a62bfc-eaab-4fed-9c55-189c4982d9b6)

Selecione o tipo de geometria como Polígono e se atente para definir a projeção como UTM 


![image](https://github.com/user-attachments/assets/d15153ed-081b-40a4-b1d5-e9cce28f6e09)


### Passo 2 - Clice no ícone de lápis (Alternar Edição) e em seguida em Adicionar Polígono (logo à direita)
![image](https://github.com/user-attachments/assets/d06542ae-560b-4823-98dd-d0295382b785)

### Passo 3 - Delimite a área  

Para isso, basta selecionar demarcar a região e, quando finalizar, clicar com o botão direito do mouse para finalizar o polígono

### Passo 4 - Exporte como GeoJSON  

![image](https://github.com/user-attachments/assets/adc57730-f639-4e7c-baa0-df3d1d514bce)

Agora, basta **salvar como GeoJSON e inserir na pasta**: ./veg_index/study_area no seu ambiente
