
# Microfone do Fone de Ouvido Não Reconhecido
Este artigo explica como corrigir o problema em que o microfone de um fone de ouvido não é reconhecido no sistema operacional Ubuntu 24.04. Embora o procedimento seja baseado no Ubuntu, é provável que funcione em outras distribuições Linux.

---

## **Passo a Passo**

### 1. Abra o arquivo de configuração do ALSA
O arquivo de configuração relevante é o **/etc/modprobe.d/alsa-base.conf**. Para editá-lo, você pode utilizar qualquer editor de texto de sua preferência. Aqui, utilizaremos o **nano**.

Execute o seguinte comando no terminal com permissões de superusuário:

``` bash
sudo nano /etc/modprobe.d/alsa-base.conf
```

### 2. Adicione as seguintes linhas ao final do arquivo

No editor de texto aberto, insira as linhas abaixo no final do arquivo:

``` bash
options snd-hda-intel model=headset-mode
options snd-hda-intel model=dell-headset-multi
```

Essas opções ajudam o sistema a identificar corretamente o microfone do fone de ouvido.

### 3. Salve as alterações e reinicie o sistema

1. Salve o arquivo:
	* No nano, pressione Ctrl + O, depois Enter para salvar.
	* Pressione Ctrl + X para sair do editor.
2. Desconecte o fone de ouvido do computador.
3. Reinicie o sistema.

### 4. Reconecte o fone de ouvido

Após a reinicialização:
1. Insira novamente o fone de ouvido.
2. Uma mensagem pode aparecer pedindo para selecionar o tipo de conexão. No meu caso, isso aconteceu após a reinicialização e inserção do fone. Se isso ocorrer, escolha a opção **Headset**.
3. Vá para Configurações > Som e selecione:
	* **Headphone** como saída de áudio.
	* **Headset Microphone** como entrada de áudio.

---

Após seguir os passos acima, o microfone do seu fone de ouvido deverá estar funcionando corretamente.
