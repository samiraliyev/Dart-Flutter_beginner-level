# Dart-Flutter_beginner-level
First part of the series talks about the basics of dart so beginners can get up to speed for the flutter tutorials. After that we will install android studio and start with the basics of flutter. At the end of the course we will create a simple ToDo App with basic functionallity.

                            ******** Methods ********** without value and with value ********
                            
  void - geriye hec bir deyer qaytarmayan methodlarin qarsisinda yazilir. 
  sayHi() methodun adidir. Her hansi hereket icra etmeyi bildirir. Methodun govdesi {} arasinda yazilir.
  Neticeni gormek ucun yuxarida esas method olan main methodunun icersinde cagirmag lazimdir.
 
void main(){
  //sayHi();
 
  sayHi("Samir");
  
  add(4, 6);
  
  print(cem(3, 7));
}

void sayHi(){
  print("hi");
}
 
 yuxarda parametrsiz method yazmisdim. indi parametr qebul eden methodlar yazim. Eyni kod yazilir,
 sadece method moterizeleri arasinda parametr gosterilir. ve parametrin tipi mutleq yazilmalidir.

void sayHi(String name){
  print("Hi $name"); // $ isaresinden istifade ederek parametri ekrana yazdirdiq.
}

void add(int x, int y){
  print(x + y);
}  

geriye integer deyer qaytardigini istediyimiz ucun methodun baslangicinda int yazdim.
ve return dedim ki, neticeni iki ededin cemi seklinde geri qaytarsin. neticeni ekrana yazdirmag ucun main methodunun icerisinde
print-den istifade edecem.

int cem(int a, int b){
  return a + b;
}


                          ********* Fat arrow functions **********
                          
  Tek setrde kod yazmaq fat arrow adlanir
  bunun ucun {} ifadesinin evezine => yazilir
     
  void main(){
     print(cem(8, 9));
  }
     
  void main() => print(cem(8, 9));
     
     
  int add(int x, int y){
     return x + y;
   }
      
   int add(int x, int y) => x + y;
      
      
                                ********** Lists ************
                                
  Her hansi bir element coxlugu demekdir. Umumi yazilisi asagidaki kimidir
  List<> myList = []
  burada <> arasinda list elementlerinin hansi tipde oldugu qeyd edilir int, String.
  List daxilinde elementler indexlenir. Birinci element 0-ci indexde yerlesir.
  Asagidaki kodda list elementlerini icerisinde 3-cu indexdeki elementi ekrana yazdirdim. 
  Eger listin icerisinde hem String hem integer hem boolean elementler varsa, onda, listin tipini dynamic olarag qeyd edirik.
  Her 3 tipe aid kod yaziram.
     
  main(){
  
   List<int> myList = [2,4,6,8];
   print(myList[3]);
       
   List<String> names = ["Samir", "Leyla", "Metin", "Nurman"];
   print(names[2]);
       
   List<dynamic> differentTypes =[true, 32, 3.14, "Adam", false];
   print(differentTypes[2]);
 }
      
      
      
      
                                       ********* For loop *********
                                       
 Loop haqqinda List uzerinden izah elemeye calisacam. Asagidaki koda baxaq
 Bu kodda dedimki elimde bir listim var. Hemin list elementlerini bir-bir mene goster.
 Demeli for() icerisinde qeyd eledim ixtiyari deyisken tanimladim ve dedimki eger bu deyiskeni list elementlerinin icinde var sayarag, 
 elementleri mene goster.
                
                                       
 main(){
  
 List<String> names = ["samir", "natalia", "alisah", "vadim"];
  
  for(var name in names){
    print(name);
  }
  
  for(int n = 0; n < names.length; n ++){
    print(names[n]);
  }  
  
  for(int i = 0; i < 5; i ++){
    print(i);
  }
}                                      
                          
                          
                                          ********* Class and Objects *********
  Melesen heyvan deye bir sinif-class yaratsaq, ona aid xususiyyetler ve ona aid ilk tanimlar (ad, yash) gosterile biler. Object ise       class referans olarag cagrilir. Asagidaki kodda daha aydin izah edecem.
  Class adlari boyuk herfle yazilarda daha yaxsi olar. Class adindan sora {} yazilir. class Pet{}.
  Class daxilinde classa aid xususiyyetler ve methodlar yazila biler. main methodu icerisinde teyin olunan objecte referans olan class     adinin qarsisinda hokmen () yazilmalidir. var cat = Pet();
  
  main(){
 
  var cat = Pet();
  cat.name = "Merry";
  cat.age = 2;
  
  print(cat.age);
}


class Pet{
  String name;
  int age;
}


                                              ********* Constructor *********
Constructor her hansi hereketin basladigi yer kimi basa dusdum.
Demeli constructora variable verdim, hemin parent class arasindaki deyisenlere referans olsun deye this sozunden istifade ederek asagidaki kodu yazdim.

main(){
 
  var cat = Pet("marry", 2);
  
  print(cat.name);
  print(cat.age);
  
}


class Pet{
  String name;
  int age;
  
  Pet(String name, int age){
    this.name = name;
    this.age = age;
  }
  
  //daha qisa formada yazilisi
  Pet(this.name, this.age);
}

                                                   ********* Class methods *********
Evvelki dersde class daxilinde ona aid xususiyyetler ve methodlar yaza bileceyimizi qeyd etmisdim. Bu dersde hemin kodlara baxaq.

main(){
 
  var cat = Pet("marry", 2);
  
  print(cat.name);
  print(cat.age);
  cat.come(); //burda method cagirdigimiz ucun () istifade eledik.
  
}


class Pet{
  String name;
  int age;
  
  Pet(this.name, this.age);
  
  void come(){
    print("Marry, please come to me");
  }
}

                                                  ********* Inheritance *********
Burada parent ve child classlardan  ve bir classa aid xususiyetlerin diger classa extends yolu ile oturulmesine aid kod yazacam.
Demeli asagida iki class yazdim. Animals classi parent class ki gosterdim. ve Pet classina extends eledim yeni Animals parent olacag . Pet ise child class rolunu alacag. Koda baxanda Pet classi icerisinde age deyiskeni tanimlamadigim halda hemin deyiskeni cat objectinde cagirmisam. Kodun islemeyine sebeb extends elemeyimdir ki, Pet classini referans alan her bir object extends oldugu classin da xususiyyetlerini ozunde cemlesdire biler.

main(){
 
  var cat = Pet();
  cat.age = 4;
  
  print(cat.age);
}

class Animals{
  int age;
}

class Pet extends Animals{
  String name;
}


                                                  ********* Overriting method **********

Overriting methodlar ucun yuxardaki kodu yeniden yazib neceki, bir classda olmayan variableleri extends olmus classdan cekdiyimiz kimi o classa tanitmadigim, lakin, diger klassdan cekdiyim methodlari gosterecem.
Animal classinda method yazdim. Ve hemin methodu extends olunmus Pet classinda cagirdim. Ve overriting olarag super yazdim ki, yeni method cagirilarken get birinci parent classin icindekini oxu sora child classa gel.

main(){
 
  var cat = Pet();
  cat.name = "MM";
  cat.happyBirthday();
}

class Animal{
  int age;
  
   void happyBirthday(){
    print("Happy bithday");
  }
}

class Pet extends Animal{
  String name;
 
 void happyBirthday(){
    super.happyBirthday();
    print(name);
 }
}


                                                ********* Maps **********
Map list-e oxsuyur. Yazilisinda biraz ferg var. Map<> anyMap = {} kimi yazilir . Burada <> arasinda iki deyer yazilir key ve value, birincisi String, ikincisi ise String, int ve dynamic ola biler. Eger Map-in daxilindaki verilenler her iki terefi string olarda <> arasinda String, String yazilir. Eger key String value qarisig olacagsa, onda <String, dynamic> kimi yazilir.

void main(){
 
 Map<String, int> persons = {
   
   "Samir": 27,
   "Leman": 27,
   "Tim": 33
 };
  
  print(person["Leman"]);
}


        ********* Start App bolmesini project seklinde paylasacam **********
