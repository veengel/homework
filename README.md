# Testing #

## Tasks ##

 * Протестировать индексированный и связной список из домашней работы #3.
   Тест-кейсы должны покрывать все контракты компонентов, описанные в домашней работе #3 и 
   включать в себя позитивные и негативные сценарии.
   Протестировать все сценарии с выбросом исключений с помощью @Rule.
   При тестировании использовать jUnit 4 и hamcrest, кейсы должны быть организованы с разделением 
   на секции GIVEN-WHEN-THEN.

 * Протестировать класс Processor, зависящий от компонентов Producer и Consumer. 
   Для проверки взаимодействия Processor’а с его зависимостями использовать Mockito.
   Чтобы проверить как Processor вызывает зависимости используйте Mockito#verify().
   Чтобы проверить аргумент Consumer#consume() используйте ArgumentCaptor.
   Обязательный тест-кейс – замокать результат Producer#produce() для того, чтобы протестировать 
   негативный сценарий – выброс IllegalStateException.
  
   ```
   public class Processor { 
       private Producer producer; 
       private Consumer consumer; 

       public void process() { 
           String value = producer.produce(); 

           if (value == null) { 
               throw new IllegalStateException(); 
           } consumer.consume(value); 
        } 

       public void setProducer(Producer producer) { 
           this.producer = producer; 
        } 

       public void setConsumer(Consumer consumer) { 
           this.consumer = consumer; 
        } 
   } 

   public class Producer { 
       public String produce() { 
           return "Magic value"; 
       } 
   } 

   public class Consumer { 
       public void consume(String value) { 
           System.out.println("Consumed -> " + value); 
       } 
   }
   ```