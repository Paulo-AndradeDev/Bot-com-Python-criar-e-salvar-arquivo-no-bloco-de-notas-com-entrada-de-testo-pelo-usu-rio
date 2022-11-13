# Bot com Python 
##Automação com interação com o suário

Veja o vídeo: [no Youtube](https://pages.github.com/)

### Função: abre o bloco de notas do windows, solicita do usuário o texto e o nome do arquivo, depois salva e fecha o bloco de notas.

Este é um script Python de automação que utiliza as biblioteca PyAutoGUI e PyPerClip. A biblioteca PyPerClip foi uma solução encontrada para lidar com caracteres especiais, algo que o PyAutoGUI não aceita. Assim o texto digitado pelo usuário, via prompt(), é copiado para a área de transferência do windows com uso do método pyperclip.copy() e, posterirmente, colado no bloco de notas.

> É um script simples, mas que serve como paradigma para automatizar uma infinidade de tarefas cotidianas semelhantes.

```
import pyautogui
import pyperclip
import time

pyautogui.PAUSE = 1

# abrir o bloco de notas
pyautogui.press('win')
pyautogui.write('bloco de notas')
pyautogui.press('enter')
time.sleep(1)

# copia o texto com caracteres especiais para a área de trabalho
pyperclip.copy(pyautogui.prompt())

# cola o texto acima ao invés de digitá-lo
pyautogui.hotkey("ctrl", "v")

# salvar
pyautogui.hotkey("ctrl", "s")

# informe o nome do arquivo
pyperclip.copy(pyautogui.prompt())
pyautogui.hotkey("ctrl", "v")

# clicar no botão salvar
pyautogui.press(['tab','tab','tab','tab'])
pyautogui.press('enter')


time.sleep(1)
pyautogui.keyDown('alt')
pyautogui.press(['f4'])
pyautogui.keyUp('alt')
```

