---
title: Calculadora de Temperatura de Bulbo Úmido
tags: ["mudança climática", "python", "temperatura de bulbo úmido"]
author: "J. de Rossi Molina"
date: 2025-01-23
math: true
---
À medida que o mundo enfrenta os desafios crescentes das mudanças climáticas, entender e monitorar os fatores ambientais que impactam diretamente a saúde humana nunca foi tão crucial. 

<!--more-->

Um desses métricos críticos é a **temperatura de bulbo úmido (TBU)**, uma medida combinada de calor e umidade que fornece um indicador direto da capacidade do corpo de se resfriar através da transpiração. Ignorar essa métrica chave pode ter sérias implicações para a saúde, especialmente à medida que as mudanças climáticas provocam ondas de calor mais frequentes e severas.

## O Que é a Temperatura de Bulbo Úmido?

A temperatura de bulbo úmido representa a temperatura mais baixa à qual o ar pode ser resfriado pela evaporação da água. Ao contrário da temperatura do ar regular, ela leva em conta tanto o calor quanto a umidade, tornando-se uma medida mais precisa do estresse térmico no corpo humano.

Quando a umidade é alta, o suor evapora menos eficientemente, limitando o mecanismo natural de resfriamento do corpo. Uma temperatura de bulbo úmido de **35°C (95°F)** é considerada o limite fisiológico superior para a sobrevivência humana sob exposição prolongada. Além desse limite, mesmo indivíduos saudáveis descansando na sombra podem sucumbir à hipertermia.

O aquecimento global intensificou as ondas de calor, que agora são mais quentes, longas e mais disseminadas do que nunca. De acordo com modelos climáticos recentes, temperaturas de bulbo úmido que antes eram consideradas raras estão se tornando mais frequentes em regiões tropicais e subtropicais.

$$
\[ 
T_{wb} = T \cdot \text{atan}(0.151977 \cdot \sqrt{RH + 8.313659}) + \text{atan}(T + RH) - \text{atan}(RH - 1.676331) + 0.00391838 \cdot RH^{3/2} \cdot \text{atan}(0.023101 \cdot RH) - 4.686035 
\]
$$

### Por Que Isso é Perigoso?

- **Estresse Térmico e Riscos à Saúde**: A exposição prolongada a altas temperaturas de bulbo úmido pode levar à **exaustão por calor**, **insolação** e até à morte. Populações vulneráveis, como idosos, crianças e indivíduos com condições de saúde preexistentes, estão particularmente em risco.
- **Perigos no Local de Trabalho**: Trabalhadores ao ar livre, especialmente na agricultura, construção e outras indústrias fisicamente exigentes, enfrentam riscos aumentados de doenças relacionadas ao calor.
- **Ilhas de Calor Urbanas**: As cidades experimentam temperaturas de bulbo úmido mais altas devido à vegetação reduzida, superfícies que absorvem calor como asfalto e fluxo de ar limitado, exacerbando os riscos à saúde para as populações urbanas.

## Por Que Monitorar a Temperatura de Bulbo Úmido é Importante

Dada sua correlação direta com a saúde humana, acompanhar a temperatura de bulbo úmido é vital para se adaptar aos desafios impostos pelas mudanças climáticas. Abaixo estão as principais razões pelas quais monitorar a TBU deve ser uma prioridade:

1. **Prevenção de Doenças Relacionadas ao Calor**
Monitorar a temperatura de bulbo úmido permite alertas precoces para eventos de calor perigosos. Governos e organizações podem usar esses dados para emitir avisos de calor, abrir centros de resfriamento e promover campanhas de conscientização pública para proteger populações vulneráveis.

2. **Melhoria da Segurança no Trabalho**
Para indústrias que dependem de trabalho ao ar livre, as medições de TBU podem informar ciclos de trabalho-descanso e protocolos de hidratação, reduzindo o risco de insolação e melhorando a segurança geral dos trabalhadores. Países como o Catar já implementaram limites de temperatura de bulbo úmido para regular o trabalho ao ar livre durante o calor extremo.

3. **Planejamento Urbano e Resiliência**
As cidades podem usar dados de temperatura de bulbo úmido para orientar estratégias de planejamento urbano, como plantar mais árvores, criar áreas sombreadas e projetar edifícios com melhor ventilação. Essas medidas não apenas reduzem o estresse térmico, mas também melhoram a habitabilidade urbana geral.

4. **Preparação na Saúde**
Os sistemas de saúde podem alocar melhor os recursos, como serviços de emergência e capacidades hospitalares, antecipando os impactos na saúde relacionados às ondas de calor através de previsões de temperatura de bulbo úmido.

# Nosso Projeto - Calculadora de Temperatura de Bulbo Úmido

Você pode acessar nosso projeto [ao vivo](https://bulb-app.onrender.com).

## Visão Geral
Este projeto é um aplicativo baseado em Python projetado para calcular a temperatura de bulbo úmido usando dados de temperatura e umidade relativa obtidos da API OpenWeather. O aplicativo foi desenvolvido com Flask para servir como uma aplicação web interativa e utiliza bibliotecas como `requests` para acesso à API e `math` para cálculos.

## Estrutura do Projeto

### Diretórios e Arquivos
- **app.py**: Arquivo principal contendo a lógica do Flask e integração com a API.
- **templates/**: Contém arquivos HTML usados na interface.
  - **index.html**: Página inicial da aplicação.
- **static/**: Contém arquivos estáticos como CSS e imagens (se necessário).
- **requirements.txt**: Lista de dependências Python para o projeto.
- **README.md**: Guia rápido para instalação e uso da aplicação.

### Tecnologias e Bibliotecas Utilizadas
- **Python 3.9 ou posterior**
- **Flask**: Framework web para criar a aplicação.
- **Requests**: Para fazer requisições HTTP à API OpenWeather.
- **Gunicorn**: Para implantação em produção.
- **Docker**: Para containerização da aplicação.

## Funcionalidades
1. **Entrada de Dados**:
   - Usuários inserem o nome de uma cidade.
2. **Integração com API**:
   - O aplicativo faz uma requisição à API OpenWeather para obter dados de temperatura e umidade relativa para a cidade especificada.
3. **Cálculo da Temperatura de Bulbo Úmido**:
   - Usa a fórmula de Stull para calcular a temperatura de bulbo úmido.
4. **Interface Web**:
   - Exibe o resultado do cálculo em uma interface amigável.
5. **Alertas ao Usuário**:
   - Se a temperatura de bulbo úmido exceder 35°C, o aplicativo emite um aviso indicando condições de saúde potencialmente perigosas.

## Instalação e Configuração

### Pré-requisitos
- Python 3.9 ou posterior
- Gerenciador de pacotes `pip`
- Chave da API OpenWeather (obtenha em https://openweathermap.org/api)

### Passos de Instalação
1. Clone o repositório GitHub:
```bash
git clone https://github.com/jeronimo-molina/bulb-app.git
cd bulb-app
```
2. Crie um ambiente virtual:

```bash {filename=bash}
python3 -m venv venv
source venv/bin/activate  # No Windows, use `venv\Scripts\activate`
```
3. Instale as dependências:

```bash {filename=bash}
pip install -r requirements.txt
```

4. Configure a chave da API:

Crie um arquivo .env na raiz do projeto e adicione:
`OPENWEATHER_API_KEY=sua_chave_api_aqui`

4. Inicie o servidor Flask:

```bash {filename=bash}
flask run
```
O aplicativo estará disponível em http://127.0.0.1:5000/.

**Alternativa**: Usando Docker
Para simplificar a execução e distribuição, o projeto suporta containerização com Docker.

Certifique-se de que o Docker está instalado.

1. Construa a imagem Docker:
```bash {filename=bash}
docker build -t bulb-app .
```
2. Execute o container:
```bash {filename=bash}
docker run -d -p 5000:5000 --env-file .env bulb-app
```

O aplicativo estará disponível em http://127.0.0.1:5000/.

3. Implantação em Produção
Para executar a aplicação em produção, use Gunicorn:
```bash {filename=bash}
pip install gunicorn
```

# Comando para iniciar o servidor
`gunicorn -w 4 app:app`

Recomenda-se configurar um proxy reverso, como Nginx, para gerenciar conexões HTTP.

# Estratégias para Mitigar os Riscos de Altas Temperaturas de Bulbo Úmido

Para nos proteger dos riscos crescentes de temperaturas extremas de bulbo úmido, devemos adotar estratégias tanto **individuais** quanto **coletivas**:

## **Ações Individuais**
- Mantenha-se hidratado e evite atividades ao ar livre durante as horas de pico de calor.
- Use roupas soltas e de cores claras para facilitar a dissipação de calor.
- Use ventiladores ou ar condicionado para manter ambientes internos mais frescos.
- Monitore os relatórios meteorológicos locais para leituras de temperatura de bulbo úmido e siga os avisos de calor.

## **Ações Comunitárias e Governamentais**
- Investir em infraestrutura de monitoramento meteorológico para fornecer dados precisos e em tempo real de temperatura de bulbo úmido.
- Desenvolver políticas públicas que regulamentem o trabalho ao ar livre durante o calor extremo.
- Implementar projetos de infraestrutura verde para reduzir os efeitos das ilhas de calor urbanas.
- Fomentar a colaboração internacional para abordar as implicações mais amplas do estresse térmico induzido pelo clima.

## Temperatura de Bulbo Úmido e o Futuro da Saúde Pública

À medida que as mudanças climáticas aceleram, entender as implicações da temperatura de bulbo úmido na saúde humana não é mais opcional—é essencial. As temperaturas crescentes de bulbo úmido não apenas representam ameaças imediatas à saúde pública, mas também sobrecarregam os sistemas de saúde, interrompem economias e exacerbam desigualdades sociais.

Investir em tecnologias e políticas para monitorar e mitigar os impactos das temperaturas de bulbo úmido é crucial para construir resiliência contra os desafios inevitáveis impostos pelas mudanças climáticas. A conscientização e as medidas proativas podem salvar vidas, melhorar os resultados de saúde pública e garantir que as comunidades permaneçam seguras em um mundo cada vez mais quente.

# Conclusão

A temperatura de bulbo úmido serve como um lembrete claro de como nossa saúde está intimamente ligada ao meio ambiente. À medida que o planeta aquece, a importância de acompanhar essa métrica só crescerá. Ao entender e abordar os riscos associados às altas temperaturas de bulbo úmido, podemos nos adaptar às mudanças climáticas e proteger nossa saúde e bem-estar.

Nesta era de desafios climáticos sem precedentes, a capacidade de medir e responder aos extremos de temperatura de bulbo úmido não é apenas uma necessidade científica—é um imperativo moral.
