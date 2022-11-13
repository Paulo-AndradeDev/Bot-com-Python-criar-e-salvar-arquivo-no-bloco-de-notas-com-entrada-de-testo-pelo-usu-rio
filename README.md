# Bot com Python 
## Automação com interação com o suário

[Veja o vídeo no Youtube](https://youtu.be/5dAzXyfbBgU)

### Função: abre o bloco de notas do windows, solicita do usuário o texto e o nome do arquivo, depois salva e fecha o bloco de notas.

Este é um script Python de automação que utiliza a biblioteca PyAutoGUI e o módulo PyPerClip. 

O módulo PyPerClip foi uma solução encontrada para lidar com caracteres especiais, algo que o PyAutoGUI não aceita.

> É um script simples, mas que serve como paradigma para automatizar uma infinidade de tarefas cotidianas semelhantes.

```
import pyautogui
import pyperclip
import time

pyautogui.PAUSE = 1

# abre o bloco de notas
pyautogui.press('win')
pyautogui.write('bloco de notas')
pyautogui.press('enter')
time.sleep(1)

# solicita o texto do usuário e o copia para a área de trabalho
pyperclip.copy(pyautogui.prompt())

# cola o texto acima no bloco de notas
pyautogui.hotkey("ctrl", "v")

# inicia o salvamento do arquivo
pyautogui.hotkey("ctrl", "s")

# solicita do usuário o nome do arquivo
pyperclip.copy(pyautogui.prompt())
pyautogui.hotkey("ctrl", "v")

# clica no botão salvar
pyautogui.press(['tab','tab','tab','tab'])
pyautogui.press('enter')

# fecha o bloco de notas
time.sleep(1)
pyautogui.keyDown('alt')
pyautogui.press(['f4'])
pyautogui.keyUp('alt')
```

