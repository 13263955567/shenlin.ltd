类名首字母大写

类中变量，方法都是驼峰命名法，首字母小写



------------------------------------

对象产生步骤：

------------------------------------

1、在内存中开辟空间，存储对象的数据，其中：

    内存中栈区保存对象的引用.
    堆区保存对象的真正内容。
    类的静态属性所有对象实例共用一份，保存在初始化数据区.
    方法保存在代码区。

    $this也保存在堆区，存储的也是对象的引用。


2、执行构造函数

    这时还未返回对象的引用地址，在构造函数中想初始化对象的属性，则使用$this访问对象，$this存储的也是对象的引用。

3、返回对象的引用地址


------------------------------------

释放对象的2情况：

------------------------------------

1、页面执行完毕，PHP的回收机制自动释放对象

2、对象的引用被全部删除后（如果有多个）释放对象（unset($obj);）


------------------------------------

面向对象编程的特性：抽象，封装，继承，多态

------------------------------------

1、抽象：把一类对象的共同属性和方法抽象出来，形成类，这种思考方式就是抽象。

2、封装：把成员方法和成员属性隐藏在类中，隐藏方法的实现细节，通过Public,Protected,Private,final,static限定类成员的访问权限，数据被保护在内，只有通过授权的成员方法才可以操作。

3、继承：

4、多态：子类继承父类，通过对父类的方法重写实现多态。

------------------------------------

1、强内聚： 尽量把方法封装到类的内部

2、弱耦合：尽量开放少的方法给外部

------------------------------------

1、final定义的方法不允许子类重写

2、final定义的类不允许继承

------------------------------------

1、类外定义常量define

    define("tax","0.5");

2、类中定义常量const，访问时需要使用self::，因常量是属于类的，不属于对象

    class A{
        const tax=0.5;

        function test(){
            echo self::tax;
        }
    }


------------------------------------

函数中的静态变量

------------------------------------

function add(){
    static $a = 1;
    echo ++$a."<br/>";
}
a();
a();
a();
a();
a();

输出:

2
3
4
5

------------------------------------

类的静态方法被子类重写时也必须为静态方法

__construct方法也会被子类重写。


重载？同一个方法名，不同的参数？（PHP不支持）

------------------------------------

$this   当前对象

$self   当前类，$self所在的代码的类

$parent


------------------------------------

当所有的子类都必须有同一个方法（如鱼，鸟都有运动方法），但子类的实现又各不相同（鱼是游水，鸟是飞翔），则在父类中可将此方法定义为抽象方法，定义了抽象方法的父类必须声明为抽象类。

抽象类不能被实例化为对象。只能实例化extends了抽象类的子类。和final定义的类正好相反，final定义的类不能被继承，只能被实例化。

抽象类中的抽象方法最少个数可以为0，即抽象类中可以没有抽象方法，但只要有一个抽象方法，类就必须被声明为抽象类。即使没有抽象方法的抽象类也不能被实例化。

子类必须实现父类的抽象方法。

抽象方法没有方法体，而不是空方法体，即没有{}。

------------------------------------

如果一个抽象类中的方法都是抽象方法，则可以把整个抽象类声明为接口，用interface替换abstract class声明，同时方法前的abstract可以去掉，子类的extends改为implements

------------------------------------

魔术常量__FUNCTION__和__METHOD__: 

    __METHOD__在类里面返回的是带有类名的方法名，如：Car::run，而__FUNCTION__返回的只有方法名，如：run
    
    在类外面，两个的返回值是一样的，都是方法名：run


__FILE__:

    返回的是__FILE__所在文件的绝对路径，不受文件包含影响

------------------------------------

魔术方法；一些儿自动运行的方法。

__set($k,$v)：当对类的private属性赋值的时候自动运行。

__get($k,$v)：当对类的private属性取值的时候自动运行。

__clone：执行clone的时候自动运行 $car = clone $mycar;

__toString：输出对象实例的时候执行，如echo new Car();

__call($methodName,$args)：调用类中不存在的方法时自动运行

__isset：调用isset检测类中private变量时，会出错，添加此方法后则会自动调用此方法，不再报错

         isset用例，检测翻页：echo isset($_GET['page'])?$_GET['page']:1;

__unset：调用unset检测类中private变量时，会出错，添加此方法后则会自动调用此方法，不再报错

__sleep：序列化时自动执行，定义了此函数则需要在函数中返回要序列化的内容，类型是数组，数组元素是类中的属性名，不用包含属性值。若要全部序列化，则不写此函数默认就是全部。

__wakeup：被反序列化时自动执行

          类被序列化时只是保存的属性和值，像数据库连接的初始化等需要在反序列化时在此方法中调用其他方法进行还原。


__autoLoad($className)：在涉及到类时（如new一个类，extends一个类）页面中找不到类时，则自动执行此函数


    function __autoload($classname){
        if($classname=="Action"){
            include '../libs/common/Action.php';
        }elseif substr($classname,-6) == "Action"{
            include '../action/'.$classname.'.php';
        }elseif ($classname=='db'){
            include '../libs/common/db.php';
        }
    }

    $act1 = new Action()
    $act2 = new channelAction()

------------------------------------

下面的函数执行后即使用mm()函数替换了__autoload()函数。即再调用不存在的类时，会执行mm()函数，而不是__autoload()

spl_autoload_register('mm');

function mm($name){

}

下面的函数即会调用类a里的方法auto

spl_autoload_register(array('a','auto'));

------------------------------------

get_class_methods

1、传类名字符串
get_class_methods('teacher')

2、传对象实例
get_class_methods($obj)

------------------------------------

get_class_vars

只能传类名字符串

------------------------------------

get_object_vars

传对象实例

------------------------------------

get_parent_class

1、传类名字符串

2、传对象实例

------------------------------------

判断对象实例是否为某个类的子类

is_subclass_of($obj,'classname')

------------------------------------

interface_exists('interface_name')

------------------------------------

获得对象类名字符串，区分大小写

get_class($obj);

在类内部调用时可以省略参数

------------------------------------

get_declared_classes

以数组形式返回当前脚本定义的类

------------------------------------

get_declared_interfaces

以数组形式返回当前脚本定义的接口

------------------------------------

method_exists($obj,'methodname')

method_exists('classname','methodname')

------------------------------------

property_exists($obj,'propertyname')

property_exists('classname','propertyname')

------------------------------------

$obj instanceof ClassA

------------------------------------
