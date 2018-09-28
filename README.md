# Скрипт на bash для записи стримов с twitch.tv

запускать через консоль
> ./twitchrec c_a_k_e

Вы можете указать несколько стримов 
> ./twitchrec a_o_w c_a_k_e nastjadd strimhata

но записываться начнётся только тот, который первым будет онлайн

так что используйте screen для запуска нескольких копий скрипта с разными аргументами
> apt install screen

> yum install screen

или качайте и собирайте из исходников сами http://www.gnu.org/software/screen/

1. для работы требуется https://streamlink.github.io/install.html и curl
2. требуется получить Client-ID тут https://dev.twitch.tv/docs/v5

########################################################################

start from console
> ./twitchrec c_a_k_e

You can specify several streams
> ./twitchrec a_o_w c_a_k_e nastjadd strimhata

But only the first online stream from the list will be recorded

so use screen to run multiple copies of the script with different streams
> apt install screen

> yum install screen

or download and compile from the sources code http://www.gnu.org/software/screen/

1. requires https://streamlink.github.io/install.html and curl
2. You need to get Client-ID here https://dev.twitch.tv/docs/v5
