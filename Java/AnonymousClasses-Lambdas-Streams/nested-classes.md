# Nested classes

static | inner |
--- | ---
Non-static nested classes (inner classes) have access to other members of the enclosing class, even if they are declared private | Static nested classes do not have access to other members of the enclosing class
a static nested class is behaviorally a top-level class that has been nested in another top-level class for packaging convenience. | an inner class is associated with an instance of its enclosing class

#### Use Case
- helper classes
- encapsulation
- event-handling mechanism - UI

## Inner Classes
`DataStructureIterator iterator = this.new EvenIterator();`

- local classes
  - You can define a local class inside any block (but not interfaces - are inherently static)
  - You cannot declare static initializers or member interfaces in a local class
    - modifier 'static' is only allowed in constant variable declaration
  - capturing variables : can access local variables that are declared final or *effectively final*
- anonymous classes


Serialization of inner classes is strongly discouraged

## Shadowing
guess the output
```
public class ShadowTest {

    public int x = 0;

    class FirstLevel {

        public int x = 1;

        void methodInFirstLevel(int x) {
            System.out.println("x = " + x);
            System.out.println("this.x = " + this.x);
            System.out.println("ShadowTest.this.x = " + ShadowTest.this.x);
        }
    }

    public static void main(String... args) {
        ShadowTest st = new ShadowTest();
        ShadowTest.FirstLevel fl = st.new FirstLevel();
        fl.methodInFirstLevel(23);
    }
}
```
