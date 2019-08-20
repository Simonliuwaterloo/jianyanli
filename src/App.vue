<template>
  <div id="app">
    <div>
      <h1>Hello, I am Jianyan Li</h1>
      <h3>1A Computer Engineering | University of Waterloo</h3>
    </div>

    <div>
      <top-view :tabs="tabs" :initialTab="initialTab">
        <template slot="tab-head-skills">
          Skills
        </template>

        <template slot="tab-panel-skills">
          <h2 class="title">Skills</h2>
          <p class="description">
            <ul>
              <li>
                <b>Languages</b>: JavaScript/TypeScript, Dart, C++, Python, HTML, CSS, JSON, XML
              </li>
              <li>
                <b>Frameworks</b>: Node.js, Flutter
              </li>
              <li>
                <b>Command line</b>: Bash, PowerShell, Git, cURL, kubectl, npm
              </li>
              <li>
                <b> IDEs</b>: Android Studio, VScode, Eclipse, Vim-like editors
              </li>
              <li>
                <b>Operating systems</b>: Windows, Linux (Ubuntu, Manjaro)
              </li>
              <li>
                <b>Organizational</b>: Agile, Scrums, test-driven-development, Jira, Confluence, code reviews
              </li>
              <li>
                <b>Devops tools</b>: Docker,  Jenkins, Grafana, Kibana
              </li>
              <li>
                <b>Database</b>: MongoDB
              </li>
            </ul>
          </p>
        </template>

        <template slot="tab-head-experience">
          Experience
        </template>

        <template slot="tab-panel-experience">
          <h2 class="title">Experience</h2>
          <h4 >QA Developer - Pelmorex Corp.</h4>
          <h4>January 2019 - April 2019</h4>
          <img src="./assets/twn.png" style="float:right">
          <p class="description">
            <ul>
              <li>
                Worked on projects with test-driven-development process in an Agile environment, participated in and held scrums
              </li>
              <li>
                Collaborated with other developers to design testing strategies in order to support new features and increased website traffic
              </li>
              <li>
                Took initiative as a self-starter to independently solve bugs in Production level code
              </li>
              <li>
                Wrote and implemented tests against microservices in JavaScript
              </li>
              <li>
                Designed APIs using Express.js framework, worked with Vue.js and Nuxt.js framework, familiar with Node.js asynchronous features
              </li>
              <li>
                Tested using Jest, Mocha, Ava and PHPUnit framework, wrote end-to-end tests with Puppeteer, Selenium and created load tests with k6
              </li>
              <li>
                Wrote PowerShell scripts to schedule tests and output test outcome to file
              </li>
              <li>
                Debugged Node.js applications in docker containers and containerized several Node.js applications/tests with Docker
              </li>
              <li>
                Monitored and debugged with kubectl, Grafana and Kibana
              </li>
            </ul>
          </p>
        </template>

        <template slot="tab-head-projects">
          Projects
        </template>

        <template slot="tab-panel-projects">
          <div class="project-container">
            <div class="projects">
              <h2 class="title">Projects</h2>
              <p class="description">
                <ul>
                  <li>
                    <b>
                      Mobile Application— Meetworth
                    </b>
                    <br>
                     Created a cross-platform, open-source Flutter application called “Meetworth”  using OOP principle. Meetworth helps connect users to their friend
                     Developed UI with Flutter
                     Programmed asynchronous applications, using Dart classes like Future, Completer
                     Familiar with Google APIs, restricted API keys with Google Cloud Platform, working knowledge of releasing and monitoring an Android application with Google Play Console
                     Proficient in debugging in Android Studio
                  </li>
                  <li>
                    <b>
                    Personal Website— www.jianyanli.com
                    </b>
                    <br>
                    Wrote HTML, CSS and JavaScript code to create a webpage
                    Integrated a calculator and a slideshow using JavaScript and CSS
                  </li>
                  <li>
                    <b>
                    Python Module— k-nearest neighbors algorithm
                    </b>
                    <br>
                    Wrote a Python module that contains functions to:
                    Read data from plain text files using pandas
                    Generate a set of data using NumPy
                    Classify data using k-nearest neighbors algorithm
                    Plot data using Matplotlib
                    Create a more user-friendly module by using minimal amount of libraries
                  </li>
                </ul>
              </p>
            </div>
            <div class="slider">
               <image-slider :images="images" :initialImage="initialImage"></image-slider>
            </div>
          </div>
        </template>
        
        <template slot="tab-head-education">
          Education
        </template>

        <template slot="tab-panel-education">
          <h2 class="title">Education</h2>
          <img src="./assets/waterloo.png" style="float: right; width: 25%">
          <p class="description">
            <ul>
              <li>
                <b>
                  University of Waterloo
                <br>
                  September 2018 - September 2023
                </b>
                <br>
                Candidate for Bachelor of Applied Science in Computer Engineering
                <br>
                Finished 1A C++ course with an average of 99
                Recognized on Dean's Honours list in 1A term with an average of 92.6 percent
                President’s Scholarship of Distinction based on an high school average of 97 percent
              </li>
              <li>
                <b>
                  High School
                <br>
                  Sep 2015 - June 2018
                </b>
                <br> 
                Leader of Physics final project
                Leader of science team  that worked on 3D modeling and 3D printing
                Developed film and photo editing skills
              </li>
            </ul>
          </p>
        </template>
        
        <template slot="tab-head-contacts">
          Contacts
        </template>

        <template slot="tab-panel-contacts">
          <h2 class="title">Contacts</h2>
          <p class="description">
          <ul>
            <li>
              phone: +1 519-580-1693
            </li>
            <li>
              email: jianyan.li@edu.uwaterloo.ca
            </li>
            <li>
              github: <a href="https://github.com/simonliuwaterloo">https://github.com/simonliuwaterloo</a>
            </li>
          </ul>
          </p>
        </template>
      </top-view>
    </div>
  </div>
</template>

<script>
import TopView from './components/TopView.vue'
import ImageSlider from './components/ImageSlider.vue'

export default {
  name: 'App',
  components: {
    TopView,
    ImageSlider
  },
  data() {
    return {
      initialTab: 'skills',
      tabs: ['skills', 'experience', 'projects', 'education', 'contacts'],
      initialImage: 'MW1',
      images: ['MW1', 'MW2', 'MW3']
    };
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.slider {
  float: right;
  width: 50%;
}

.project-container {
  overflow: hidden;
  width: 100%;
}

.projects {
  float: left;
  width: 50%;
}
body, html {
  padding: 0;
  margin: 0;
  width: 100%;
  min-height: 100vh;
}
body {
  background-color: #f1cd94;
}
</style>
