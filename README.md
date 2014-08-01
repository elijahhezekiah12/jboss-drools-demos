# jboss-drools-demos

The project contains both a maven pom and a sbt built file ([SBT 0.13](http://www.scala-sbt.org/release/docs/Getting-Started/Setup.html)). 

At this point running from sbt no longer works.
 It did work, but having again some problems (different ones this time)

## List of demos

 1. **simple** Most basic Drools demo (stateless) 
 2. **dsl** Example showing the DSL support
 3. **fire** Example from Drools documentation 


## Some Scala helpers

In this project i am using two Scala traits 'StatelessKieSessionSupport' 
and 'StatefulKieSessionSupport' to make it easier to write demos

Example:

```scala
object SomeDemo extends App with StatefulKieSessionSupport {

   override val sessionName: String = "ksessionName"
   
   ksession.foo // from the trait

}
```

These traits on their turn use the `KieContainerSupport` which checks for errors and 
initialises the kieContainer
