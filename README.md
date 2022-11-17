# exemplo-de-alteracao-de-texto-cod-java



Exemplo 1. Converter palavras para maiúsculo:
List<String> output = wordList.stream().
// Mapa de toda a lista de String em maiúsculo.
map(String::toUpperCase).
// Converte o stream para uma lista.
collect(Collectors.toList());


Exemplo 2. Procurar as palavras 
com tamanho par na lista:
List<String> output = wordList. 
stream(). 
//Seleciona somente as palavras com tamanho par.
filter(w -> (w.length() & 1 == 0). 
collect(Collectors.toList()); 


Exemplo 3. Contar as linhas de um arquivo:
long count = bufferedReader. 
// Recebe um stream com linhas individuais. 
Esse é o novo método do
// bufferedReader que retorna um stream<string>.
lines(). 
// Conta os elementos do stream de entrada.
count(); 


Exemplo 4. Juntar as linhas 3 e 4 em uma única String:
String output = bufferedReader. 
lines(). 
// Pula as duas primeiras linhas.
skip(2).
// limita a stream a apenas as próximas duas linhas.
limit(2).
// Concatena as linhas.
collect(Collectors.joining()); 


Exemplo 5. Encotrar o tamanho da linha mais longa 
em um arquivo:
int longest = reader.lines().
mapToInt(String::length). 
// cria um novo stream com o tamanho das strings mapeando
// a atual String ao tamanho correspondente.
max(). 
// Coleta o maior elemento do stream de tamanho (como 
uma optionalInt)
getAsInt();
// Atualiza o OptionalInt com um int.


Exemplo 6. Coleção de todas as palavras do arquivo
em uma lista:
List<String> output = reader. 
lines(). 
flatMap(line -> Stream.of(line.split(REGEXP))). 
// Recebe um stream de palavras de
// todas as linhas.
filter(word -> word.length() > 0). 
// Filtra as Strings vazias.
collect(Collectors.toList()); 
// Cria a lista de retorno.


Exemplo 7. Retorna a lista de palavras 
minúscula em ordem alfabética:
List<String> output = reader.lines(). 
flatMap(line -> Stream.of(line.split(REGEXP))). 
filter(word -> word.length() > 0). 
map(String::toLowerCase). 
// Atualiza o Stream da fonte com o Stream de
// letras minúsculas.
sorted(). 
// Atualiza o stream com a versão ordenada.
collect(Collectors.toList()); 
// Cria e retorna uma Lista
