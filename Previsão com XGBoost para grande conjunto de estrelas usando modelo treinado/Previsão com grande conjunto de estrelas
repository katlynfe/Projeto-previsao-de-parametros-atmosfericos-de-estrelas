# 

Este código foi testado em estrelas com temperaturas efetivas entre 3000 K e 6000 K. As mesmas estrelas do output foram separadas em treino e teste e foi salvo o modelo. Com o modelo pronto (modelo_treinado.model), utilizei as mesmas estrelas para a previsão. São em torno de 850 estrelas.

#




import glob
import numpy as np


# Pasta com espectros
caminho_pasta = '/home/katlyn/Downloads/Pesquisa/Baixar espectros da fonte - APOGEE/output'

# Lista de arquivos txt
arquivos_txt = glob.glob(caminho_pasta + '/*.txt')

pr=[]

# Loop através dos arquivos txt
for arquivo_txt in arquivos_txt:
    # Carregar o espectro estelar a partir do arquivo txt
    espectro = np.loadtxt(arquivo_txt)
    # Redimensionar o espectro para que tenha a mesma forma que os dados de treinamento
    fluxo_data = espectro[:, 1]
    
    # Carregar o modelo treinado
    model = xgb.XGBRegressor()
    model.load_model('/home/katlyn/Downloads/Pesquisa/Baixar espectros da fonte - APOGEE/modelo_treinado.model')  # Substitua pelo caminho correto para o seu modelo treinad
    
    
    # Usa o modelo para prever os parâmetros atmosféricos da estrela com o espectro fornecido
    parametros = model.predict(fluxo_data.reshape(1, -1))
    # Imprime o nome do arquivo atual
    print(f'Arquivo: {arquivo_txt}')
    # Imprime os parâmetros preditos
    atm = ['\t''TEFF', 'LOG G', 'Fe/H']
    for nome in atm:
        print('{:15}'.format(nome), end='')
    print()
    print(parametros)
