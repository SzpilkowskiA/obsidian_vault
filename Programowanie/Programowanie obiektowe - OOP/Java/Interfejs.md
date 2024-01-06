Interfejs to zestaw metod i zmiennych bez ich implementacji. Właściwa implementacja interfejsu znajduje się w implementującej go klasie. 
- Metody - publiczna oraz abstrakcyjna
- Zmienne - publiczna, statyczna oraz finalna
```
interface nazwaInterfejsu {
    int wyplata();
}
```
```
class Pracownik implements nazwaInterfejsu {
	penjsa = 5000;
	
	@Override
	public void wyplata(){
		System.out.println("Zarobki wynoszą: " + this.pensja)
	}
}
```
### Interfejs funkcyjny
