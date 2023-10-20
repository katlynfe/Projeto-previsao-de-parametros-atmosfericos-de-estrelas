# Projeto previsão de parametros atmosféricos de estrelas
 Este projeto foi realizado em várias etapas com o foco na melhor previsão dos valores de parâmetros atmosféricos de variadas estrelas.

##
### Como foi feito?

Primeiramente, após alguns estudos, foi escolhido o XGBoost, pois melhor se encaixava nos requisitos. Então dividiu-se em alguns testes e treinos para fazer as previsões. Basicamente dois modelos foram criados para cada teste e treino: o comum usando o fluxo retirado do espectro da estrela, e o outro foi feito se baseando em uma estrela com características simulares ao do Sol e retirou-se da literatura linhas de absorção dessa estrela. Assim criou-se um recorte de fluxo nesses intervalos de comprimento de onda e fluxo. O código de ambos para os dois tipos de teste e treino são encontrados nas pastas. Com o fluxo de ambos, cria-se o modelo de previsão Regressor. Com o modelo criado, basta salvá-lo e aplicá-lo nas estrelas de interesse para a previsão ser realizada. Neste caso foram aplicadas nas próprias estrelas de teste e treino, uma são anãs com exoplanetas e a outra se trata de estrelas aleatórias com exoplanetas.
Os códigos foram feitos usando a linguagem Python e são encontrados cada um deles, assim como os códigos de extração de fluxo, nas pastas.
