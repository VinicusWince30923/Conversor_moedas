<!DOCTYPE html>
<html>
<head>
  
</head>
<body>

<h1>Conversor de Moedas</h1>

<p>Este repositório contém um script Python para converter valores entre três moedas: Real brasileiro, Dólar americano e Euro. O script solicita ao usuário a entrada do valor e da moeda a ser convertida, realiza as conversões e exibe os resultados.</p>


<h2>Código do projeto</h2>
<pre>
<code>
#Função para converter valor em Real para outras moedas
def converter_real():
    try:
        valor = float(input("Insira aqui o valor desejado: "))  # Solicita e converte o valor inserido pelo usuário em float
    
    except ValueError: 
        print("Por favor, insira um valor válido.")  # Captura exceção se o valor não puder ser convertido para float
        return None, None, None  # Retorna valores nulos se a entrada não for válida
    
    # Realiza as conversões para Dólar americano e Euro
    conversao_para_USA = valor / 5.51
    conversao_para_Euro = valor / 5.89
    
    return conversao_para_USA, conversao_para_Euro, valor


#Função para converter valor em Dólar para outras moedas
def converter_dolar():
    try:
        valor = float(input("Insira aqui o valor desejado: "))  # Solicita e converte o valor inserido pelo usuário em float
    except ValueError: 
        print("Por favor, insira um valor válido.")  # Captura exceção se o valor não puder ser convertido para float
        return None, None, None  # Retorna valores nulos se a entrada não for válida
    
    # Realiza as conversões para Real brasileiro e Euro
    conversao_para_Real = valor * 5.51
    conversao_para_Euro = valor / 1.07
    
    return conversao_para_Real, conversao_para_Euro, valor


#Função para converter valor em Euro para outras moedas
def converter_Euro():
    try:
        valor = float(input("Insira aqui o valor desejado: "))  # Solicita e converte o valor inserido pelo usuário em float
    except ValueError: 
        print("Por favor, insira um valor válido.")  # Captura exceção se o valor não puder ser convertido para float
        return None, None, None  # Retorna valores nulos se a entrada não for válida
    
    # Realiza as conversões para Real brasileiro e Dólar americano
    conversao_para_Real = valor * 5.89
    conversao_para_Dolar = valor * 1.07
    
    return conversao_para_Real, conversao_para_Dolar, valor


#Função principal para converter moedas
def conversor_moedas(moeda):
    
    if moeda == "real brasileiro":
        # Se a moeda escolhida for Real brasileiro, solicita o valor a ser convertido
        
        print("Agora insira o valor a ser convertido.")
        
        # Chama a função converter_real() para realizar as conversões
        valor_convertido_para_USA, valor_convertido_para_Euro, mostrar_valor = converter_real()
        
        # Verifica se o valor inserido foi válido
        if mostrar_valor is not None:
            
            # Se válido, exibe o valor inserido e os resultados das conversões para Dólar americano e Euro
            print(f"O valor inserido foi: R${mostrar_valor}\n")
            print(f"De {moeda.capitalize()} para Dólar americano fica em: US${valor_convertido_para_USA:.2f}")
            print(f"De {moeda.capitalize()} para Euro fica em: €{valor_convertido_para_Euro:.2f}")
            
    
    elif moeda == "dolar americano" or moeda == "dólar americano":
        # Se a moeda escolhida for Dólar americano, solicita o valor a ser convertido
        
        print("Agora insira o valor a ser convertido.")
        
        # Chama a função converter_dolar() para realizar as conversões
        valor_convertido_para_Real, valor_convertido_para_Euro, mostrar_valor = converter_dolar()
        
        
        # Verifica se o valor inserido foi válido
        if mostrar_valor is not None:
            
            # Se válido, exibe o valor inserido e os resultados das conversões para Real brasileiro e Euro
            print(f"O valor inserido foi: US${mostrar_valor}\n")
            print(f"De {moeda.capitalize()} para Real brasileiro fica em: R${valor_convertido_para_Real:.2f}")
            print(f"De {moeda.capitalize()} para Euro fica em: €{valor_convertido_para_Euro:.2f}")
            
    
    elif moeda == "euro":
        # Se a moeda escolhida for Euro, solicita o valor a ser convertido
        
        print("Agora insira o valor a ser convertido.")
        
        # Chama a função converter_Euro() para realizar as conversões
        valor_convertido_para_Real, valor_convertido_para_Dolar, mostrar_valor = converter_Euro()
        
        
        # Verifica se o valor inserido foi válido
        if mostrar_valor is not None:
            
            # Se válido, exibe o valor inserido e os resultados das conversões para Real brasileiro e Dólar americano
            print(f"O valor inserido foi: €{mostrar_valor}\n")
            print(f"De {moeda.capitalize()} para Real brasileiro fica em: R${valor_convertido_para_Real:.2f}")
            print(f"De {moeda.capitalize()} para Dólar americano fica em: US${valor_convertido_para_Dolar:.2f}")

    else:
        # Se a moeda escolhida não for reconhecida, exibe uma mensagem de erro
        print("Não trabalhamos com essa moeda ainda. Por favor, escolha entre: Real brasileiro, Dólar americano ou Euro")

        
#Início do programa principal
print("Bem vindo ao conversor de moedas! \n")

print("Aqui você pode converter três moedas entre si, seriam essas: Real brasileiro, Dólar e Euro. \n")

print("Em seguida, escolha qual a moeda entre as três citadas que deseja converter.")

moeda = str(input("Insira qual será convertida: ")).lower()  # Solicita ao usuário a escolha da moeda e converte para minúsculas

print(f"A moeda selecionada é: {moeda.capitalize()} \n")

#Chamando a função principal do conversor de moedas
conversor_moedas(moeda)
</code>
</pre> 

<h2>Estrutura do Código</h2>

<p>O código está organizado em funções que lidam com a conversão de valores entre as diferentes moedas e uma função principal que coordena a conversão baseada na moeda escolhida pelo usuário.</p>

<h3>Lista de Funções</h3>
<ul>
    <li><strong>converter_real()</strong>
        <ul>
            <li>Solicita ao usuário o valor em Real brasileiro.</li>
            <li>Converte o valor para Dólar americano e Euro.</li>
            <li>Retorna os valores convertidos e o valor original.</li>
        </ul>
    </li>
    <li><strong>converter_dolar()</strong>
        <ul>
            <li>Solicita ao usuário o valor em Dólar americano.</li>
            <li>Converte o valor para Real brasileiro e Euro.</li>
            <li>Retorna os valores convertidos e o valor original.</li>
        </ul>
    </li>
    <li><strong>converter_Euro()</strong>
        <ul>
            <li>Solicita ao usuário o valor em Euro.</li>
            <li>Converte o valor para Real brasileiro e Dólar americano.</li>
            <li>Retorna os valores convertidos e o valor original.</li>
        </ul>
    </li>
    <li><strong>conversor_moedas(moeda)</strong>
        <ul>
            <li>Coordena a conversão de acordo com a moeda escolhida pelo usuário.</li>
            <li>Solicita o valor a ser convertido e exibe os resultados das conversões.</li>
            <li>Trata erros de entrada de valores.</li>
        </ul>
    </li>
</ul>

<h2>Requisitos do Sistema</h2>
<p>Para rodar a aplicação, são necessários os seguintes requisitos do sistema:</p>
<ul>
    <li><strong>Sistema Operacional:</strong> Windows 7 ou superior, macOS 10.13 ou superior, ou distribuições Linux modernas.</li>
    <li><strong>Python:</strong> Python 3.6 ou superior.</li>
    <li><strong>Espaço em Disco:</strong> Pelo menos 100 MB de espaço livre.</li>
    <li><strong>Memória RAM:</strong> Pelo menos 1 GB de RAM.</li>
</ul>

<h2>Execução</h2>
<p>Para executar o script de conversão de moedas utilizando o Visual Studio Code (VSCode), siga os passos abaixo:</p>
<ol>
    <li>Abra o Visual Studio Code.</li>
    <li>Certifique-se de que a extensão do Python está instalada no VSCode. Caso não esteja, você pode instalá-la a partir da aba de extensões.</li>
    <li>Baixe o script Python do repositório e salve-o em um diretório de sua escolha.</li>
    <li>No VSCode, clique em <strong>File</strong> > <strong>Open Folder</strong> e navegue até o diretório onde o script foi salvo. Abra esse diretório.</li> 
    <li>Clique duas vezes no arquivo do script para abri-lo no editor.</li>
    <li>Com o arquivo aberto, clique no botão "Run" no canto superior direito (Símbolo de "Play") ou pressione <code>F5</code> para executar o script.</li>
</ol>
<h3>Exemplo de Uso</h3>
<ol>
    <li>O usuário será solicitado a inserir a moeda que deseja converter (Real brasileiro, Dólar americano ou Euro).</li>
    <li>Para a moeda escolhida, o usuário deve fornecer o valor a ser convertido.</li>
    <li>O script realizará as conversões para as outras duas moedas e exibirá os resultados.</li>
</ol>
