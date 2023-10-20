#

Este código foi feito utilizando o recorte de fluxo nos intervalos:
linhas = {
        'Linhas Fe I Red G': [15194.492, 15207.528, 15395.718, 15490.339, 15648.515, 15964.867, 16040.657, 16153.247, 16165.032],
        'Linhas Co': [15570, 15970, 16184, 16600],
        'Linhas CI': [15784.7, 16005.0, 16021.7],
        'Linhas CN': [15260, 15322, 15397, 15332, 15410, 15447, 15466, 15472, 15482, 15580.88],
        'Linhas OH': [15278.334, 15568.780, 16190.263, 16192.208],
        'Linhas Na I': [16373.853, 16388.858],
        'Linhas Mg I': [15740.716, 15748.988, 15765.842, 15879.5, 15886.2, 15954.477],
        'Linhas Al I': [16718.957, 16750.564, 16763.360],
        'Linhas Si I': [15361.161, 15376.831, 15888.410, 15960.063, 16060.009, 16094.787, 16215.67, 16680.770, 16828.159],
        'Linhas K I': [15163.067, 15168.376],
        'Linhas Ca I': [16136.823, 16150.763, 16155.236, 16157.364],
        'Linhas Ti I': [15334.847, 15543.756, 15602.842, 15698.979, 15715.573, 16635.161],
        'Linhas V I': [15924.0],
        'Linhas Cr I': [15680.063],
        'Linhas Mn I': [15159.0, 15217.0, 15262.0]
    }
    
    
Depois que extraiu-se esse fluxo, ele foi reorganizado para que o código compreendesse todas as estrelas e foi criado o modelo de previsão.

#




import pandas as pd
import xgboost as xgb

# Carregar o modelo treinado
model = xgb.XGBRegressor()
model.load_model('/home/katlyn/Downloads/Pesquisa/Baixar espectros da fonte - APOGEE/modeloFluxoReorganizado.model') 

# Carregar os fluxos reorganizados para as estrelas de teste a partir do arquivo CSV
caminho_fluxos_teste = '/home/katlyn/Downloads/Pesquisa/Baixar espectros da fonte - APOGEE/fluxos_reorganizados.csv' 
fluxos_teste_df = pd.read_csv(caminho_fluxos_teste, header=None)  # Assumindo que não há cabeçalho no CSV

# Fazer previsões para todos os conjuntos de fluxos de teste
previsoes = model.predict(fluxos_teste_df)

# Organizar as previsões em um DataFrame
previsoes_df = pd.DataFrame(previsoes, columns=['TEFF', 'LOGG', 'MG_FE'])
previsoes_df
