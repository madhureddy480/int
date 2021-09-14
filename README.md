

## Java Memory: 

### Static/Class Level : 
this stores byte code and static variables; they are kept in memory until class in unloaded.
### Heap: 
get’s created when an object is instantiated ; stores class level variables and instance variables
### Stack: 
method level. One for each method. Stores local variables; garbage collected end of the method.


## Int palindrome:

    Int actualNumber = 12345654321;
    Int remainder = 0;
    Int reversedNumber = 0;

    while(actualNumber  !=  0){
      Remainder = actualnumber % 10;
    reversedNumber = reversedNumber * 10 + remainder;
    actualNumber = actualNumber / 10; 
    } 
    if(actualNumber == reversedNumber){
      Sysout(“palindrome”);
    }


## String reverse:

    String s = “madhu”
    Byte[] b = s.getbytes();

    Byte[] bReverse = new byte[b.length];
    Int j = 0;
    for(int i = b.length -1; i>=0; i--){
      bReverse[j] = b[i];
               j++;
    }

    Sting reverse = new String(bReverse);

## Int[] palindrome: 

      int half = i.arr.length/2;
	  	int length = i.arr.length;
	  	boolean someFlag = false;
		for( int startIndex = 0 ; startIndex <= half ; startIndex++ ) {
			
			System.out.println(i.arr[startIndex]);

			System.out.println(i.arr[length - startIndex - 1]);

			if(i.arr[startIndex] != i.arr[length - startIndex - 1]) {
				System.out.println("not");
				someFlag = true;
				break;
			}
		}
		if(!someFlag)
		  System.out.println("yes");

## Class Loaders:

Application/System Class Loader
Extension Class Loader
Bootstrap Class Loader

Class.forName() → full name; 

## Implements Serializable:

Serialization is a process where you want to store the state of an object to a physical storage (series of bytes) like file system and load it when required.

Is platform independent
static and transient member variables are not stored.

InvalidClassException

    Class clasName Implements Serializable interface
    {
	    FileOutputStream fs = new FileOutputStream(new File(“c://h.txt”);
    	ObjectOutputStream os = new ObjectOutputStream(fs);
  	os.writeObject(new String(“Nadu”));
  	os.close();
	  fs.close();

	FileInputStream fis = new FileInputStream(new File(“c://h.txt”));
	ObjectInputStream ois = new ObjectInputStream(fis);
	String s = (String)ois.readObject();

	  ois.close();
    fis.close();

    }
## Array reverse Inplace
    public class ArrayReverseInplace {

      public static void main(String[] args) {
        int[] array = {1,2,3,5,6};

        for(int i = 0 ; i < array.length/2; i++) {
          int temp1 = array[i];
          int temp2 = array[array.length-1-i];
          array[i] = temp2;
          array[array.length-1-i] = temp1;
        }

        for(int a: array)
        System.out.println(a);

      }
    }

##  List Map



![Screen Shot 2021-09-14 at 12 10 24 AM](https://user-images.githubusercontent.com/13371445/133193647-294623e6-49fd-4eb7-a4d5-f127712628a4.png)


## Comparable Comporator

### Comparable --> natural ordering of elements ; must implement Comparable interface ; e1.compareTo(e2) ; Collections.sort(list)
### Comparator --> custom comparisions ; multiple types of comparisions ; extra comparator classes per need.
![Screen Shot 2021-09-14 at 9 51 17 AM](https://user-images.githubusercontent.com/13371445/133270376-1ac36f72-95f5-40dc-95ea-c89758a52071.png)


## Spring Scopes
Singleton
Request
Prototype
Session
GlobalSession

## SpringIOC

Spring Inversion of Control is letting Spring Framework takecare of Spring bean creation, initialization, setting up properties, autowiring, configuration though Dependency Injection and at the end of the life cyle destroying the bean. Here we define the configuration, autowiring and all using XMLs or Annotations and Spring manages these beans.

## SpringBean Life Cycle
 container start
 bean initiatlization
 dependecy injection through autowiring
 bean metadata setup like, SetBeanName, SetBeanFactory, SetApplicationContext, 
 preInit
 PostConstruct
 and finally preDestroy and Destroy
 
 ## Hibernate Object States
 ###### transient --> object is just created by java
 ###### persist --> object is saved to db
 ###### detached --> session is closed
 
 HQL is DB independent
 Dialect specifies the type of the database used in the application/hibernate
 
 ## Java 8
 <img width="703" alt="Screen Shot 2021-09-14 at 1 09 20 PM" src="https://user-images.githubusercontent.com/13371445/133302797-c337fc73-78a9-4a85-bdf5-2b30cf78321f.png">
 
 ## Streams
 	List<String> list = Arrays.asList("Hello","Madhu","Interview");

	private void hello() {
		
		List<String> c = list.stream().filter(e -> hasSomeValuee(e)).collect(Collectors.toList());	
		System.out.println(c +"hhh");
		System.out.println(list+"hhh");//both are same
		
		c = list.stream().map( e -> updateValue(e)).collect(Collectors.toList());
		System.out.println(c +"hhh");//created new
		System.out.println(list+"hhh");
		
		boolean f = list.stream().anyMatch( e-> hasSomeValuee(e));
		System.out.println(f);
	}
	
	private String updateValue(String e) {
		e = e+"1";//returning some object
		return e;
	}
	
	private boolean hasSomeValuee(String e) {
		e = e+"1";//no impact ; always return boolean
		return true;
	}
