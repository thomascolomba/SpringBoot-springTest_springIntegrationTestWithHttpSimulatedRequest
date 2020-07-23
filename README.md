Run tests simulating GET request within spring stack.<br/>
<br/>
compile & execute :<br/>
mvn spring-boot:run<br/>

during the execution, at the url : http://localhost:8080/<br/>
The application shows : Hello, World<br/>
<br/>
--HomeController.java<br/>
@RequestMapping("/")<br/>
public @ResponseBody String greeting() {<br/>
&nbsp;&nbsp;return <b>return "Hello, World";</b><br/>
--IntegrationTestHttpLikeRequestTest.java<br/>
@Test<br/>
public void greetingShouldReturnDefaultMessage() throws Exception {<br/>
&nbsp;&nbsp;<b>assertThat</b>(this.restTemplate.<b>get</b>ForObject("http://localhost:" + port + "/",String.class))<br/>
&nbsp;&nbsp;&nbsp;&nbsp;.contains("Hello, World");<br/>
--performs a GET at the url "/" and checks the returned String contains "Hello, World".<br/>
<br/>
