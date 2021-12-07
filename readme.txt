Estes programas foram testados com o Python na versão 3.9.7

# denumberfy.exe
================

O programa "denumberfy.exe" removerá os índices de parágrafos em um arquivo no formato "SRT". Exemplo:

- Considere um arquivo chamado "legenda.srt", com o seguinte conteúdo:

  -------- início do arquivo ----------
  1
  00:00:08,468 --> 00:00:14,749
  Primeira legenda

  2
  00:00:14,765 --> 00:00:18,450
  Segunda legenda
  
  3
  00:00:18,646 --> 00:00:23,995
  Terceira legenda
  --------- fim do arquivo -------------

então no prompt de comandos (terminal), após executar o comando

  denumberfy.exe legenda.srt

o arquivo em questão (legenda.srt) passará a ter o seguinte conteúdo:

  -------- início do arquivo ----------
   
  00:00:08,468 --> 00:00:14,749
  Primeira legenda

   
  00:00:14,765 --> 00:00:18,450
  Segunda legenda
  
   
  00:00:18,646 --> 00:00:23,995
  Terceira legenda
  --------- fim do arquivo -------------

ou seja, o programa "denumberfy.exe" remove todos os índices de parágrafos, sem remover suas linhas.

Observação: não se preocupe com as linhas duplicadas, pois estas serão consertadas com o programa "numberfy.exe".

# numberfy.exe
================

Este programa fará o inverso do programa "denumberfy.exe", ou seja, recebendo uma sequência de parágrafos não numerados, este fará a inserção dos índices na ordem certa. Exemplo:

- Considere um arquivo chamado "legenda.srt", com o seguinte conteúdo:

  -------- início do arquivo ----------
  00:00:08,468 --> 00:00:14,749
  Primeira legenda

  00:00:14,765 --> 00:00:18,450
  Segunda legenda (seguida de várias linhas em branco)
  


   
  00:00:18,646 --> 00:00:23,995
  Terceira legenda
  --------- fim do arquivo -------------

então no prompt de comandos (terminal), após executar o comando

  numberfy.exe legenda.srt

o arquivo em questão (legenda.srt) passará a ter o seguinte conteúdo:

  -------- início do arquivo ----------
  1
  00:00:08,468 --> 00:00:14,749
  Primeira legenda

  2
  00:00:14,765 --> 00:00:18,450
  Segunda legenda (seguida de várias linhas em branco)

  3
  00:00:18,646 --> 00:00:23,995
  Terceira legenda
  --------- fim do arquivo -------------

ou seja, todas as linhas em branco duplicadas são unificadas, bem como é inseridos todos os índices na ordem correta, resolvendo assim vários problemas de uma vez só.

# srt2txt.exe e txt2srt.exe
===========================

Estes dois programas fazem a conversão de srt para txt e txt para srt, respectivamente. Vale ressaltar que essa conversão nada mais é do que o renomeamento da extensão do arquivo em questão. Exemplos:

1) srt para txt. Considere um arquivo chamado "legenda.srt". Então o seguinte comando

  srt2txt.exe legenda.srt

renomeará o arquivo "legenda.srt" para "legenda.txt"

2) srt para txt. Faz exatamente o inverso, e seu é, portanto, análogo.

# Como executar em ambiente Linux ou Mac?
=========================================

Para executar em sistemas Unixes, basta usar o próprio código fonte e chamá-lo usando o interpretador do Python. Por exemplo, o programa numberfy.exe, será usado assim

   python numberfy.py legenda.srt

   ou      

   ./numberfy.py legenda.srt

em vez de assim (ambiente Windows)

   numberfy.exe legenda.srt
