# Introduction to K6 Testing
Have you ever wondered where you can get enough friends to test your application all at the same time? 
Well, fear not because K6 is the only friend you'll need!
In this article I'm going to teach you how to become a K6 wizard! 🧙

I will show you why it's used and how to setup/use it to test your application.
I will explain what K6 is, what Load Testing is and the different types of testing that can be done with K6.

## What is this K6 Magic? 🪄
---
K6 or Grafana K6 is an open-source load testing tool that makes it easy to performance test your application making you a more productive developer.
With K6 you can run a variety of different types of load tests while monitoring the performance of your application continuously.
You can simulate different traffic to see how your application performs in a varienty of scenarios.

## Testing types 🧪 
---
With K6 there are a varienty of supported testing methods like Load Testing, Spike Testing & Soak Testing. The results of each type of testing will give different insights about your system & how it performs allowing you the developer to improve your system.

`Load Testing` 🏋️ is all about bullying your application with alot of concurrent users/requests and monitoring your system's suffering.

`Spike Testing` doesn't casually increase the load on your system, it gives your application a mini heart attack by throwing a large load at the system in a short period of time. Did I say this happens multiple times? Talk about cruelty!

Unlike what the name might suggest your system does not get to relax in a warm bath, instead `Soak Testing` 🛀 places your system under constant load for an extended period of time so that you can see how reliable your system is and how it might perform over long periods of time under load.

## Advantages of K6 💪
---
K6 has many advantages like the fact that it uses a minimal amount of system resources (ie: RAM, CPU, HDD/SSD) to conduct extensive tests on your system.

K6 provides excellent monitoring options to observe on your system while it's hard at work.  

## Some Limitations 🚧
---
We all have our limits and K6 is no exception since it was created by human beings like you and I (assuming you're human).

K6 unfortunately doesnt display web pages the same way that a browser might. This means that if your system uses libraries that use some kind of browser APIs, those will not be compatible. However, because of this K6 has greatly improved performance as it consumes less resources.

## Setting up K6
---
Right, now the fun bit. Let's get you up and running with K6. What do you need? Well first we need to install it, how we do that depends on your operating system.

Linux (Debian/Ubuntu)
```sh
sudo gpg --no-default-keyring --keyring /usr/share/keyrings/k6-archive-keyring.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys C5AD17C747E3415A3642D57D77C6C491D6AC1D69
echo "deb [signed-by=/usr/share/keyrings/k6-archive-keyring.gpg] https://dl.k6.io/deb stable main" | sudo tee /etc/apt/sources.list.d/k6.list
sudo apt-get update
sudo apt-get install k6
```

MacOS (using Homebrew)
```sh
brew install k6
```

Windows
```sh
# Chocolatey package manager
choco install k6

# OR

# Windows Package Manager
winget install k6
```

Now that you have it installed, congratulations!

## Running a K6 Load Test
---
Ok NOW is the fun bit, I promise!

Here is what you need to run your first load test, just paste this into your VIM editor cause you're cool and save as `script.js`.

```js
import http from 'k6/http';
import { sleep } from 'k6';

export default function () {
  http.get('https://test.k6.io');
  sleep(1);
}
```
Now, to run the test just run this command:

```sh
k6 run script.js
```

Ok great, what did that just do? 

Well this just simply send one `GET` reguest to `https://test.k6.io` and then sleeps for one millisecond.



## What are Virtual Users (VUs)?

## What are Scenarios?

## What are Executors?

## Metrics 📈

## Result Visualization 📊
