# Regular expessions/Serialization #

## Task ##

Написать программу, которая будет анализировать этот файл и выводить статистику:
N самых длинных операций для каждого модуля, длительность операции и время, когда операция закончилась. 
Операции должны быть отсортированы по имени модуля и в порядке убывания времени выполнения.

### Требования ###
 
Возможность сериализовать и десериализовать результаты анализа в/из файл(а). Загружать и показывать результаты анализа логов из файла. Программа должна поддерживать флаги коммандной строки:
-file <path_to_logs_file>
-load <path_to_saved_results>
-view N
-save <path_to_saved_results>

## This program takes command-line arguments with mentioned-above flags

:heavy_minus_sign: -file - after this flag you need to specify file "deserialized.txt" (this file contains results of parsed logs after deserialization)

:heavy_minus_sign: -load - after this flag you need to specify file "logs_result.dat" (after this command the mentioned file will appear, it contains results of parsed logs after serialization)

:heavy_minus_sign: -view - after this flag you need to specify the number of top operations to be shown in each module

:heavy_minus_sign: -save - after this flag you can specify file "deserialized.txt" if you want result of "-view" operation to be saved


* To build project execute in cmd: 

> mvn clean install

:exclamation: To run application execute in cmd:

### Examples ###

:black_medium_small_square: To load results of parsing and serialization:

> java -jar ./target/homework-jar-with-dependencies.jar -load logs_result.dat

:white_check_mark: Result:
> Done.
You will see the file "logs_result.dat".

:black_medium_small_square: To get the result of deserialisation "logs_result.dat":

> java -jar ./target/homework-jar-with-dependencies.jar -file deserialized.txt

:white_check_mark: Result:
> Done.
You will see the file "deserialized.txt".

:black_medium_small_square: To view top 5 operations in "deserialized.txt":

> java -jar ./target/homework-jar-with-dependencies.jar -file deserial
ized.txt -view 5

:white_check_mark: Result:
> Done.
> ASC Module:
> "Save Order"   50995 ms, finished at 2018-07-12 17:32:07.735
> "Login"        50988 ms, finished at 2018-07-23 04:39:16.160
> "Logout"       50986 ms, finished at 2018-07-23 17:33:49.394
> "Find Product" 50983 ms, finished at 2018-07-27 02:31:30.727
> "Login"        50981 ms, finished at 2018-07-14 20:39:52.217
> CMN Module:
> "Get Order"    50999 ms, finished at 2018-07-24 01:10:55.073
...

:black_medium_small_square: To save results in "deserialized.txt" of top 10 operations:

> java -jar ./target/homework-jar-with-dependencies.jar -view 10 -save deserialized.txt 

:white_check_mark: Result:
> ASC Module:
> "Save Order"   50995 ms, finished at 2018-07-12 17:32:07.735
> "Login"        50988 ms, finished at 2018-07-23 04:39:16.160
> "Logout"       50986 ms, finished at 2018-07-23 17:33:49.394
> "Find Product" 50983 ms, finished at 2018-07-27 02:31:30.727
...
> Done.