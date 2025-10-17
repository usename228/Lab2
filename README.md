Лабораторна робота №2 uart
Виконав АС-31 Ніколаєнко А. Г.

1)  Виконаємо конфігурацію пінів контроллера як зображено на рис. 1
   <img width="760" height="641" alt="image" src="https://github.com/user-attachments/assets/58d6ede1-0ee7-4ec1-ab0d-5a574859da89" />
   де USART1_RX та USART1_TX - відповідно лінії прийому та відпавки данних інтерфейсу USART 
   Налаштуємо USART на асинхронний прийом данних 
   <img width="460" height="482" alt="image" src="https://github.com/user-attachments/assets/c9bdd418-72dc-4d8e-b10b-66dd282ddd1e" />
   USB_OTG_FS_DP , USB_OTG_FS_DM для двухнапрямленої передачі данних по шинам Data+ і Data- інтерфейса USB на повній швидкості до 12Mbps
   Налаштуємо USB на передачу данних по Virual Com Port а також режим Device_only який говорит контроллеру виступати в якості підключеного присторою який при ініциалізації відповідає на запити, надає свої дескриптори, відправляє/приймає дані
   <img width="452" height="486" alt="image" src="https://github.com/user-attachments/assets/6d566549-c52a-422d-aa94-867494cc50a3" />
   <img width="445" height="504" alt="image" src="https://github.com/user-attachments/assets/0bc142e0-1e50-4a97-8e61-c61a06fc31c7" />

3)  Тепер напишимо код який буде відправляти і отримувати данні по цим двом інтерфейсам
   <img width="471" height="215" alt="image" src="https://github.com/user-attachments/assets/21a8e50b-7912-4f93-b0cd-a56ca534c6b6" />
   Створюємо змінні rx, tx для обробки данних.
   Змінні tx, rx бажано оголосити до int main(), щоб вони були глобальними та дебагер мав можливість відстежувати їх.
   Як варінт ці змінні можна оголосити static, щоб вони не вважалися локальним і після відпрацювання функції main() вони не видалились при розгортці стека.

 4) Пеперевіримо роботу коду підключивши LogicAnalyzer до відповідних пінів USART, а USB до ПК і отримаємо щосб накшталт
    <img width="597" height="128" alt="image" src="https://github.com/user-attachments/assets/07eba6ed-14e2-4036-84de-f6bc1a78e651" />
    Для перевірки USB відкриємо моніторинг COM порта в ArduinoIDE 

    

    

