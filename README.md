https://youtrack.jetbrains.com/issue/KT-30283

```shell
$ ./gradlew[.bat] classes
$ cd build/classes
$ javap -p java/main/InJava.class >InJava.class.txt
$ javap -p kotlin/main/InKotlinKt.class >InKotlinKt.class.txt
```

InJava.class.txt:
```
Compiled from "InJava.java"
public class InJava {
  public InJava();
  public static void enumList(java.util.List<MyEnum>);
  public static java.util.List<MyEnum> enumList();
  public static void enumSet(java.util.Set<MyEnum>);
  public static java.util.Set<MyEnum> enumSet();
  public static void enumIterable(java.lang.Iterable<MyEnum>);
  public static java.lang.Iterable<MyEnum> enumIterable();
  public static void intList(java.util.List<java.lang.Integer>);
  public static java.util.List<java.lang.Integer> intList();
  public static void intSet(java.util.Set<java.lang.Integer>);
  public static java.util.Set<java.lang.Integer> intSet();
  public static void intIterable(java.lang.Iterable<java.lang.Integer>);
  public static java.lang.Iterable<java.lang.Integer> intIterable();
}
```

InKotlinKt.class.txt:
```
Compiled from "InKotlin.kt"
public final class InKotlinKt {
  public static final void enumList(java.util.List<? extends MyEnum>);
  public static final java.util.List<MyEnum> enumList();
  public static final void enumSet(java.util.Set<? extends MyEnum>);
  public static final java.util.Set<MyEnum> enumSet();
  public static final void enumIterable(java.lang.Iterable<? extends MyEnum>);
  public static final java.lang.Iterable<MyEnum> enumIterable();
  public static final void intList(java.util.List<java.lang.Integer>);
  public static final java.util.List<java.lang.Integer> intList();
  public static final void intSet(java.util.Set<java.lang.Integer>);
  public static final java.util.Set<java.lang.Integer> intSet();
  public static final void intIterable(java.lang.Iterable<java.lang.Integer>);
  public static final java.lang.Iterable<java.lang.Integer> intIterable();
}
```
