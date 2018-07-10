# Testing #

## Tasks ##

 * �������������� ��������������� � ������� ������ �� �������� ������ #3.
   ����-����� ������ ��������� ��� ��������� �����������, ��������� � �������� ������ #3 � 
   �������� � ���� ���������� � ���������� ��������.
   �������������� ��� �������� � �������� ���������� � ������� @Rule.
   ��� ������������ ������������ jUnit 4 � hamcrest, ����� ������ ���� ������������ � ����������� 
   �� ������ GIVEN-WHEN-THEN.

 * �������������� ����� Processor, ��������� �� ����������� Producer � Consumer. 
   ��� �������� �������������� Processor�� � ��� ������������� ������������ Mockito.
   ����� ��������� ��� Processor �������� ����������� ����������� Mockito#verify().
   ����� ��������� �������� Consumer#consume() ����������� ArgumentCaptor.
   ������������ ����-���� � �������� ��������� Producer#produce() ��� ����, ����� �������������� 
   ���������� �������� � ������ IllegalStateException.
  
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