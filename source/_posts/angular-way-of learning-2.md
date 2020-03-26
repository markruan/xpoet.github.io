---
title: Angular从入门到放弃（二） Angular对比Vue和React
date: 2018-08-05 23:20:14
tags: [Angular]
categories: [Angular]
---
> 作为一个菜鸟，在讨论Angular、React和Vue的优缺点上，确实没有发言权，为此找到一篇非常好的文章，原文出处：https://www.codeinwp.com/blog/angular-vs-vue-vs-react/

![angular-vs-react-vs-vue](https://iotvnaw69daj.i.optimole.com/w:1018/h:518/q:auto/https://mk0codeinwp10tp0961a.kinstacdn.com/wp-content/uploads/2019/01/angular-vs-vue-vs-react.jpg)
Just about a year ago, developers were mainly debating on whether they should be using Angular or React for their projects. But over the course of 2018, we saw a growth of interest in a third player called Vue.js. Looking forward into 2019, this post is a comprehensive guide on which is perhaps the right solution for you: Angular vs React vs Vue.

If you are a developer starting out on a project and cannot decide on which JavaScript framework to use, this guide should help you make a decision.

We cover various aspects of Angular, Vue, and React to see how they suit your needs. This post is not just a guide on Angular vs React vs Vue but aims to provide a structure to help judge front-end JavaScript frameworks in general. In case a new framework arrives next year, you will know exactly what parameters to look at!

*In this post, we assume that you have basic knowledge of JavaScript and have used JavaScript frameworks as well.*

#### Part 1: A brief history of Vue vs React vs Angular
Before we get into the technical details, let’s first talk about the history behind these frameworks – just to better appreciate their philosophy and their evolution over time.
**How it all started 🐣**

**Angular**, developed by Google, was first released in 2010, making it the oldest of the lot. It is a TypeScript based JavaScript framework. A substantial shift occurred in 2016 on the release of Angular 2 (and the dropping of the “JS” from the original name – AngularJS). Angular 2+ is known as just Angular. Although AngularJS (version 1) still gets updates, we will focus the discussion on Angular. The latest stable version is Angular 7, which was released in October 2018.

**Vue**, also known as Vue.js, is the youngest member of the group. It was developed by ex-Google employee Evan You in 2014. Over the last two years, Vue has seen a substantial shift in popularity, even though it doesn’t have the backing of a large company. The current stable version is 2.17, released in August 2018. Vue’s contributors are supported by Patreon. Vue 3, currently in the prototyping phase is planning to move to TypeScript.

**React**, developed by Facebook, was initially released in 2013. Facebook uses React extensively in their products (Facebook, Instagram, and WhatsApp). The current stable version in 16.X, released in November 2018.


Here’s a short summary of Angular vs React vs Vue, in terms of their status and history:

**The history of Angular vs React vs Vue**

|  | Angular | React | Vue |
|:---------:|:--------:|:--------:|:--------:|
| Initial release | 2010 | 2013 | 2014 |
| Official site | angular.io | reactjs.org | vuejs.org |
| Approx. size (KB) | 500 | 100 | 80 |
| Used by | Google | Wix, Facebook | Alibaba, GitLab |

**License 👮‍♂️**
Before you use an open source framework, make sure you go through its license. Interestingly, all three frameworks use the MIT license, which provides limited restrictions on reuse, even in proprietary software. Make sure you know the implications of the license before using any framework or software.

Here is a quick summary of the MIT license in plain English terms.

**Popularity 🔥**
As “angular” and “react” are common words, it is difficult to grasp their popularity from Google Trends. Though, a good proxy for their popularity is the number of stars that their GitHub repositories get. A sudden shift in the number of stars of Vue occurred in mid-2016 and, recently, Vue has been up there with React as the most popular frameworks.

![](https://iotvnaw69daj.i.optimole.com/w:692/h:414/q:auto/https://mk0codeinwp10tp0961a.kinstacdn.com/wp-content/uploads/2018/12/img-1.png)
_Number of stars on GitHub projects for Angular, React, and Vue_

Let us check how the job market is for Angular vs React vs Vue, which is also a good measure of popularity:

***

#### Part 2: Community and development
Now that you are familiar with the history and trends of each of these frameworks, we will look at the community to assess the development of these frameworks. We have already seen that for all of the frameworks, a major release has been shipped in the last four months, which indicates that development is going on in full swing.

Let us look at Angular vs React vs Vue with respect to statistics on their GitHub repositories:

|  | Angular | React | Vue |
|:---------:|:--------:|:--------:|:--------:|
| # Watchers | 3.3k | 3.7k | 5.7k |
| # Stars | 43k | 71k | 122k |
| # Forks | 11k | 16k | 17k |
| # Commits in last month | 446 | 339 | 81 |
| # Contributors | 798 | 1.8k |	240 |

Vue has a huge number of watchers, stars and forks. This shows its popularity among users and its value when comparing Vue vs React. However, the number of commits and contributors for Vue are lower than Angular and React.

One possible explanation is that **Vue is driven entirely by the open source community, whereas Angular and React have a significant share of Google and Facebook employees contributing to the repositories.**

From the statistics, all three projects show significant development activity, and this is surely going to continue in the future — just these statistics cannot be the basis of not deciding to use either of them.

***

#### Part 3: Migrations
As you’re working with your framework of choice, you don’t want to have to worry about a framework update coming along and messing up your code. Though in most cases you won’t encounter many issues from one version to another, it’s important to keep your finger on the pulse because some updates can be more significant and require tweaks to keep things compatible.

Angular plans major updates every six months. There is also a period of another six months before any major APIs are deprecated, which gives you the time of two release cycles (one year) to make necessary changes if any.

When it comes to Angular vs React, Facebook has stated that stability is of utmost importance to them, as huge companies like Twitter and Airbnb use React. Upgrades through versions are generally the easiest in React, with scripts such as react-codemod helping you to migrate.

In the FAQ section for Migration, Vue mentions that 90% of the APIs are same if you are migrating from 1.x to 2. There is a migration helper tool that works on the console to assess the status of your app.

***

#### Part 4: Working with the frameworks
There are a handful of important characteristics to look at here, chief of them being overall size and load times, the components available, and learning curve.

**Size and load times ⏲️**
The sizes of the libraries are as follows:
- Angular: 500+ KB
- React: 100 KB
- Vue: 80 KB  

Although there is a significant difference between the sizes of the frameworks, they are still small as compared to the average webpage size (2+ MB in 2018). Additionally, if you use a popular CDN to load these libraries, it is highly probable that a user has the library already loaded in their local system.

**Components 🏗️**
Components are integral parts of all three frameworks, no matter if we’re talking Vue, React, or Angular. A component generally gets an input, and changes behavior based on it. This behavior change generally manifests as a change in the UI of some part of the page. The use of components makes it easy to reuse code. A component may be a cart on an e-commerce site or a login box on a social network.

**Angular**:
In Angular, components are referred to as directives. Directives are just markers on DOM elements, which Angular can track and attach specific behavior too. Therefore, Angular separates the UI part of components as attributes of HTML tags, and their behaviors in the form of JavaScript code, this is what sets it apart when looking at Angular vs React.

**React**:
React, interestingly, combines the UI and behavior of components. For instance, here is the code to create a hello world component in React. In React, the same part of the code is responsible for creating a UI element and dictating its behavior.

**Vue**:
In Vue, UI and behavior are also a part of components, which makes things more intuitive when looking at Vue vs React. Also, Vue is highly customizable, which allows you to combine the UI and behavior of components from within a script. Further, you can also use pre-processors in Vue rather than CSS, which is a great functionality. Vue is great when it comes to integration with other libraries, like Bootstrap.
To compare how the same app looks with different libraries, here is a great post on creating the same to do list app on React and Vue and contrasting the differences of the two frameworks.

Although Angular, React and Vue have a significant learning curve, their uses upon mastery are limitless. For instance, you can integrate Angular and React with WordPress and WooCommerce to create progressive web apps.

***

**Angular vs React vs Vue: Who wins?**
Towards the end of this post, let us recall the characteristic features of each framework to try to answer the question: Angular vs React vs Vue: which one should you choose?

**Angular** is the most mature of the frameworks, has good backing in terms of contributors and is a complete package.
However, the learning curve is steep and concepts of development in Angular may put off new developers.
Angular is a good choice for companies with large teams and developers who already use TypeScript.

**React** is just old enough to be mature and has a huge number of contributions from the community. It is gaining widespread acceptance. The job market for React is really good, and the future for this framework looks bright.
React looks like a good choice for someone getting started with front-end JavaScript frameworks, startups and developers who like some flexibility. The ability to integrate with other frameworks seamlessly gives it a great advantage for those who would like some flexibility in their code.

**Vue** is new to the arena, without the backing of a major company.
However, it has done really well in the last few years to come out as a strong competitor for Angular and React. This is perhaps playing a role with a lot of Chinese giants like Alibaba and Baidu picking Vue as their primary front-end JavaScript framework.
However, it remains to be seen how it does in the future and one is justified to be cautious with it. Vue should be your choice if you prefer simplicity, but also like flexibility.

The answer to the debate of Angular vs React vs Vue is that there’s no absolute right choice, which you’ve probably expected.

Each of these libraries has their own benefits and drawbacks. Based on the project you’re working on, and your individual requirements, one of them is going to be more suitable than the others. It’s always key to do your own research before deciding, especially if you’re going to be working on a business venture and not on a personal project.