# Klasy abstrakcyjne
## Wstęp
W przypadku, gdy [[Klasy|klasa]] jest zbyt ogólna, aby mogła pełnić istotną rolę w programie można ją zadeklarować jako klasę abstrakcyjną. Nie będzie można tworzyć [[Obiekty|obiektów]] danej klasy, a będzie raczej czymś w rodzaju szablonu dla klas potomnych (które będą zawierały wszystkie jej składowe elementy).

Jakie niesie to ze sobą korzyści? Dzięki zastosowaniu klasy abstrakcyjnej można napisać metodę abstrakcyjną, która nie ma implementacji, a jedynie wiadomo, że taka metoda przyda się w obiektach klas potomnych.

Ważną cechą klas abstrakcyjnych jest to, że mogą zawierać zarówno metody abstrakcyjne jak i w pełni zaimplementowane. W związku z tym jeśli metoda w pełni jest poprawna w całej hierarchii, to należy ją umieścić możliwie wysoko, nawet w klasie abstrakcyjnej.