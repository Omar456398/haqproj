<template>
  <SearchBar
    @updateSearchEmit="handleSearchChange"
    :numberOfPosts="this.results.length"
  ></SearchBar>
  <SearchResult v-for="(item, key) in this.results" :searchString="this.searchText" :item="item" :key="key" :isFirst="key === 0"></SearchResult>
</template>

<script>
import SearchBar from "./components/SearchBar.vue";
import SearchResult from "./components/SearchResult.vue";

export default {
  name: "App",
  data() {
    return {
      articles: [
        {
          title: "Introduction to JavaScript",
          article:
            "Learn the basics of JavaScript, one of the most popular programming languages used for web development.",
          epoch: 1729018816256,
          id: 1,
        },
        {
          title: "Understanding Asynchronous Programming",
          article:
            "Dive deep into the world of asynchronous programming in JavaScript, including promises, async/await, and callbacks.",
          epoch: 1728718816256,
          id: 2,
        },
        {
          title: "Getting Started with Python",
          article:
            "An introduction to Python programming, a versatile language known for its simplicity and wide-ranging applications.",
          epoch: 1728418816256,
          id: 3,
        },
        {
          title: "Mastering Data Structures",
          article:
            "Explore key data structures like arrays, linked lists, stacks, and queues, and learn how they are implemented in different languages.",
          epoch: 1728118816256,
          id: 4,
        },
        {
          title: "Object-Oriented Programming in Java",
          article:
            "Understand the principles of object-oriented programming (OOP) in Java and how to apply inheritance, polymorphism, and encapsulation.",
          epoch: 1727818816256,
          id: 5,
        },
        {
          title: "Version Control with Git",
          article:
            "Learn the fundamentals of Git, the most widely used version control system, and how to manage project versions effectively.",
          epoch: 1727518816256,
          id: 6,
        },
        {
          title: "Building REST APIs with Node.js",
          article:
            "Discover how to create scalable REST APIs using Node.js and Express, complete with CRUD operations and middleware.",
          epoch: 1727218816256,
          id: 7,
        },
        {
          title: "Introduction to Machine Learning",
          article:
            "A beginner’s guide to machine learning, covering key concepts like supervised learning, unsupervised learning, and algorithms.",
          epoch: 1726918816256,
          id: 8,
        },
        {
          title: "CSS Flexbox and Grid Layout",
          article:
            "Master layout design for responsive websites using CSS Flexbox and Grid to create flexible, grid-based page designs.",
          epoch: 1726618816256,
          id: 9,
        },
        {
          title: "Working with Databases in SQL",
          article:
            "Learn how to design, query, and manage relational databases using SQL, the standard language for database management.",
          epoch: 1726318816256,
          id: 10,
        },
        {
          title: "Functional Programming in JavaScript",
          article:
            "Explore functional programming concepts like pure functions, higher-order functions, and immutability in JavaScript.",
          epoch: 1726018816256,
          id: 11,
        },
        {
          title: "Debugging Techniques in Python",
          article:
            "Learn essential debugging techniques and tools in Python to identify and resolve issues in your code efficiently.",
          epoch: 1725718816256,
          id: 12,
        },
        {
          title: "Introduction to TypeScript",
          article:
            "TypeScript extends JavaScript by adding static types. Learn how to get started with TypeScript for scalable web applications.",
          epoch: 1725418816256,
          id: 13,
        },
        {
          title: "Web Development with React",
          article:
            "Get a complete guide to building interactive user interfaces with React, focusing on components, hooks, and state management.",
          epoch: 1725118816256,
          id: 14,
        },
        {
          title: "Algorithms: Sorting and Searching",
          article:
            "Understand core algorithms for sorting and searching, such as bubble sort, merge sort, quicksort, and binary search.",
          epoch: 1724818816256,
          id: 15,
        },
        {
          title: "Introduction to Cloud Computing with AWS",
          article:
            "Learn the basics of cloud computing and how to deploy applications on Amazon Web Services (AWS) infrastructure.",
          epoch: 1724518816256,
          id: 16,
        },
        {
          title: "DevOps and Continuous Integration",
          article:
            "An overview of DevOps principles and how continuous integration/continuous deployment (CI/CD) pipelines streamline software development.",
          epoch: 1724218816256,
          id: 17,
        },
        {
          title: "Writing Efficient Code",
          article:
            "Learn how to write code that is both time- and space-efficient, with tips on optimizing performance and reducing complexity.",
          epoch: 1723918816256,
          id: 18,
        },
        {
          title: "Introduction to Blockchain Development",
          article:
            "Discover the fundamentals of blockchain technology and how to build decentralized applications (dApps) using smart contracts.",
          epoch: 1723618816256,
          id: 19,
        },
        {
          title: "Securing Web Applications",
          article:
            "Learn how to protect web applications from common vulnerabilities such as SQL injection, cross-site scripting (XSS), and CSRF.",
          epoch: 1723318816256,
          id: 20,
        },
      ],
      searchText: "",
    };
  },
  computed: {
    results() {
      return this.articles.filter(item => item.title.toLowerCase().includes(this.searchText.toLowerCase()) || item.article.toLowerCase().includes(this.searchText.toLowerCase()));
    },
  },
  methods: {
    handleSearchChange(value) {
      this.searchText = value;
    },
  },
  components: {
    SearchBar,
    SearchResult,
  },
};
</script>
