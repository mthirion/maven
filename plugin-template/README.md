# Template maven plugin

This is a template for Maven plugins development

Plugins are simple java classes annotated with @Mojo (name="goalName" ,  defaultPhase = LifecyclePhase.XXX )
The class extends AbstractMojo, which defines the void exectute() method.
This method can throw 2 exceptions: MojoExecutionException and MojoFailureException

Plugin parameters (<configuration>) are defined using the @Parameter (defaultValue = "", property = "propName", required = true) annotation
The <configuration> value/subtags will depends on the parameter type.

getLog() can be used to get the default console logger


After compiling and installing the plugin (mvn install), the plugin can be tested with:
 mvn <groupId>:<artifactId>:<version>:goal

To shorten it to <artifact-prefix>:goal, add the groupId to the <pluginGroups> section of the settings.xml:
  <pluginGroups>
      <pluginGroup>integration.redhat.org</pluginGroup>
  </pluginGroups>


