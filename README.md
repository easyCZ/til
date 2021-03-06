Today I learned...
======
#### 2017-01-18 To run tests in Rust in `tests` directory which use `src` files, you need to reference the package name
* `src/lib.rs`
```
pub fn hello() {
    println!("Hello, world!");
}
```
* `tests/my_test.rs`
```
extern crate hello_world;

#[test]
fn test_prints_hello() { assert_eq!("Hello, world!", hello_world::hello()); }
```
where `hello_world` is the project/package name

#### 2017-01-16 Use CMD-Shift-C to open Element selector in Chrome

#### 2017-01-15 Ownership in Rust through a intro_rust() tutorial
[intro_rust()](http://intorust.com/)

#### 2017-01-14 Learned about the Vinyl industry

#### 2017-01-13 Define a Rust package with `mod`
```
[pub] mod my {
    // Items in modules default to private visibility.
    fn private_function() {
        println!("called `my::private_function()`");
    }

    // Use the `pub` modifier to override default visibility.
    pub fn function() {
        println!("called `my::function()`");
    }
}
```

#### 2017-01-12 The first byte of a PNG document is the signature
The PNG singature is composed of the following ASCII values:
* 137	A byte with its most significant bit set (8-bit character)
* 80	P
* 78	N
* 71	G
* 13	Carriage-return (CR) character, a.k.a. CTRL-M or ^M
* 10	Line-feed (LF) character, a.k.a. CTRL-J or ^J
* 26	CTRL-Z or ^Z
* 10	Line-feed (LF) character, a.k.a. CTRL-J or ^J

#### 2017-01-11 It is possible to pack arbitrary content into a PNG file
It is then possible to pack HTML/CSS/JS into the content and serve it as ana image. [Arbitrary PNG content](https://news.ycombinator.com/item?id=9319526)

#### 2017-01-10 Add 2^5 (32) to any ASCII uppercase character to obtain the lowercase
Similarly, substract 32 from any ASCII lowercase character to obtain the uppercase.
```
a = chr(ord('A') + 32)
A = chr(ord('a') - 32)
```

#### 2016-11-23 Configure [httpie](https://httpie.org/) timeout with a default config
```
~/.httpie/config.json
```
```
"default_options": ["--style=fruity", "--body"]
```

#### 2016-11-22 AWS Lambda Environment Variables
It is now possible to specify environment variables in AWS Lambda

#### 2016-11-21 Mockito Argument Captor with Generics
```
@Captor
private ArgumentCaptor<Pair<String, Account>> accountCaptor;

@Test
public void argumentCaptor() {
  when(service.disableAccount(account.capture()).thenReturn(...);
  Pair<String, Account> accountArgument = accountCaptor.get();
  ...
}
```

#### 2016-11-18 Pipe input into a `curl` command 
```
echo "payload" | curl -d @-
```

#### 2016-05-12 Easy git directory publish with [git-directory-deploy](https://github.com/X1011/git-directory-deploy)

#### 2016-05-10 Discovered [Elm Lang](http://elm-lang.org/)

#### 2016-05-09 MPI, pthreads and Julia

#### 2016-05-08 Linux insides
[GitBook](https://www.gitbook.com/book/0xax/linux-insides/details)

#### 2016-05-02 Use git-flow
[CheatSheet](https://gist.github.com/kristopherjohnson/8979538)

#### 2016-04-26 Use async-await in React Native Redux Action Creators for more win
```javascript
async function makeAction() : Promise<Object> {
  const data = await Async.get(...);
  return { type: 'ACTION_TYPE', data };
}
```

#### 2016-04-25 Close the current HTML tag (including ReactJS) in Sublime Text
```
CMD+ALT+.
```

#### 2016-04-24 Select All Inside Current Scope in Sublime Text 
```
CTRL+SHIFT+M
```
#### 2016-04-23 List Globally Installed NPM packages
```bash
npm list -g --depth=0
```

#### 2016-04-22 Spin Infinitely in React Native
```javascript
class SpinningSquare extends React.Component {

  state = {
    rotation: new Animated.Value(0)
  }
  
  /* Duration drives the speed of each rotation */
  componentDidMount() {
    const timingConfig = { toValue: 1, duration: 1000, easing: Easing.linear }
    this.animation = Animated.timing(this.state.rotation, timingConfig)
    this._animate()
  }
  
  _animate = () => {
    this.state.rotation.setValue(0);  // Needs to be reset after a full rotation
    this.animation.start(this._animate);  // self as callback onFinished
  }
  
  render() {
    const rotate = this.state.rotation.interpolate({ inputRange: [0, 1], outputRange: ['0deg', '360deg'] })
    return (
      <Animated.View style={{
        width: 40,
        height: 40,
        backgroundColor: 'red',
        transform: [{ rotate }]
      }} />
    )
  }
}
```


#### 2016-04-13
Learned some vim commands through `vimtutor`

#### 2016-04-12
Learned how to use iOS Facebook login with the Facebook SDK

#### 2016-04-11
How to use Firebase as a messagining queue with [firebase-queue](https://github.com/firebase/firebase-queue)

#### 2016-04-09
Loading the BIOS after the power button is pressed on a pc

#### 2016-04-02
How to use FP with lodash

#### 2016-03-30
Learned how exhausting finishing a dissertation is :)

#### 2016-03-28
How objects and inheratiance works in Go from [build-web-applications-with-golang](https://www.gitbook.com/book/astaxie/build-web-application-with-golang/details)

#### 2016-03-26
Memcached performance drastically increases with thread pinning and IRQ pinning.

#### 2016-03-25
Investigated how IRQ affinity works. Learned you can obtian the number of interrupts executed on a given CPU core through `cat /proc/interrupt` as well as how setting IRQ Affinity to a given CPU/CPUs works. We can provide the list of values in `/proc/irq/<irq_id>/smp_affinity_list`.

#### 2016-03-24
Learned about functors, Maybe, Either and IO from [mostly-adequate-guide](https://drboolean.gitbooks.io/mostly-adequate-guide/content/)

#### 2016-03-23
Functional programming with JavaScript through the awesome [mostly-adequate-guide](https://drboolean.gitbooks.io/mostly-adequate-guide/content/). 

