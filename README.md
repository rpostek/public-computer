# public-computer
Komputer ogólnodostepny

1. Instalacja Windows 10 oraz sterowników
1. Aktywacja Windows
Klucz rejestracyjny bądź z nalepki, bądź do wyciągnięcia z BIOSu (z wiersza poleceń):  
```wmic path softwarelicensingservice get OA3xOriginalProductKey```
1. Tworzenie użytkownika "Visitor" bez hasła należącego do grupy "goście" (z wiersza poleceń):
```
net user Visitor /add /active:yes
net user Visitor *
net localgroup użytkownicy Visitor /delete
net localgroup goście Visitor /add
```
1. Usuwanie profilu uzytkownika "Visitor" przy wylogowywaniu.  
Do usuwania profilu "Visitor" wykorzystuje się program delprof2.exe. Jego dokumentacje i pobieranie na 
[stronie producenta](https://helgeklein.com/free-tools/delprof2-user-profile-deletion-tool/).
Program uruchamia się z Harmonogramu zadań na zdarzenie wylogowywania.  
- Program skopiować do c:\windows\system32
- W Harmonogramie otworzyć kreator zadań "Akcja" -> "Utwórz zadanie podstawowe..."
- Nazwa zadania "Usuń profil", <kbd> Dalej&gt; </kbd>
- "Przy rejestrowaniu okreslonego zdarzenia", <kbd> Dalej&gt; </kbd>
- Dziennik: "Zabezpieczenia", Źródło: "Microsoft Windows security auditing.", Identyfikator zdarzenia: "4647", <kbd> Dalej&gt; </kbd>
- Akcja: "Uruchom program", <kbd> Dalej&gt; </kbd>
- 
