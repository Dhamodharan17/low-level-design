#### The Object class only provides a default no-argument constructor
```
public Object() {
    // Default constructor logic
}
```
#### When there is no constructor -> JVM will create a default constructor and call parent constructor
```
public class Box {
    Box(){
        System.out.println("Parent Constructor");
    }
}

class BoxWeight extends Box{
    // when there is no contructor 
    // JVM will create a default constructor and call parent constructor
}

class Main{
    public static void main(String[] args) {
        BoxWeight boxWeight = new BoxWeight();
    }
}
```
#### JVM will not create default constructor when we have our own so we must call it from child constructor
```
public class Box {
    
    // when there is args constuctor, JVM will not create default constructor
    // From child we must call the args constructor otherwise C.E
    Box(String message){
        System.out.println("Parent Constructor says "+message);
    }
}

class BoxWeight extends Box{
// call from child
    BoxWeight(){
        super("Hello");
        System.out.println("Child Constructor");
    }

}

class Main{
    public static void main(String[] args) {
        BoxWeight boxWeight = new BoxWeight();
    }
}
```
