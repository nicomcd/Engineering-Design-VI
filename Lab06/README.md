*I pledge my Honor that I have abided by the Stevens Honor System*

- Study the GitHub repository Lesson 6
- Install Node.js and run hello-world.js, hello.js, and http.js
- Refresh the webpage to see server activities
- Install Pystache and run say_hello.py that uses the template in say_hello.mustache


The following code block contains the commands from the lab assignment and its respective output:


### Lab 6A: Node.js
```
$ sudo apt install nodejs
$ node -v
v12.22.9
$ sudo apt install npm
$ npm -v
8.5.1
$ node -h
```
`node -h` outputs the help menu for nodejs:
![image](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/ec958e26-2907-467c-bf6d-14cb16f3c25c)

```
$ cd ~/iot/lesson6
$ node hello-world.js
Server running at http://127.0.0.1:3000/
```
![image](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/64ed0575-f128-4aec-b421-f3d723292c3d0)

```
$ node hello.js
Server running at http://127.0.0.1:8080/
response end call done
request end event fired
```
![image](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/1191bf24-97af-481c-9ea1-acb238bc0006)


```
$ node http.js
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
```
![image](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/787c3cfd-2062-452a-84d3-4cb8c7241017)

### Lab 6B: Pystache

```
$ sudo pip3 install pystache
$ cd ~/iot/lesson6
$ cat say_hello.mustache
Hello, {{to}}!
$ cat say_hello.py

# https://github.com/defunkt/pystache
import pystache
print(pystache.render('Hi {{person}}!', {'person': 'Alexa'}))

# Create dedicated view classes to hold view logic
class SayHello(object):
    def to(self):
        return "World"
hello = SayHello()

# Use template in say_hello.mustache
renderer = pystache.Renderer()
print(renderer.render(hello))

# Pre-parse a template
parsed = pystache.parse('Hey {{#who}}{{.}}!{{/who}}')
print(parsed)
print(renderer.render(parsed, {'who': 'Google'}))
print(renderer.render(parsed, {'who': 'Siri'}))

$ python3 say_hello.py
Hi Alexa!
Hello, World!

['Hey ', _SectionNode(key='who', index_begin=12, index_end=18, parsed=[_EscapeNode(key='.'), '!'])]
Hey Google!
Hey Siri!
```

![image](https://github.com/nicomcd/Engineering-Design-VI/assets/35404943/ae3136ea-ab49-44e1-83ad-3c9ca3295c18)


