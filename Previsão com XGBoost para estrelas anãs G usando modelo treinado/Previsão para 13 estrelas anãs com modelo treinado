#

Este código foi treinado e testado por estrelas anãs, ao todo 13. Foi usado seu espectro, carregado o modelo treinado e feito a previsão com as mesmas estrelas.

#



import glob
import xgboost as xgb


# Pasta com espectros
caminho_pasta = '/home/katlyn/Downloads/Pesquisa/Baixar espectros da fonte - APOGEE/Estrelas com exoplanetas 13/output2'

# Lista de arquivos txt
arquivos_txt = glob.glob(caminho_pasta + '/*.txt')


model = xgb.XGBRegressor()
model.load_model('/home/katlyn/Downloads/Pesquisa/Baixar espectros da fonte - APOGEE/Estrelas com exoplanetas 13/modelo_treinado_estrelas_exoplanetas.model')



# Loop através dos arquivos txt
for arquivo_txt in arquivos_txt:
    # Carregar o espectro estelar a partir do arquivo txt
    espectro = np.loadtxt(arquivo_txt)
    # Redimensionar o espectro para que tenha a mesma forma que os dados de treinamento
    fluxo_data = espectro[:, 1]
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
