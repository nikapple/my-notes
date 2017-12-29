# Apache Velocity Templates

- Velocity is a Java-based template engine. It permits anyone to use a simple yet powerful template language to reference objects defined in Java code.

- Velocity's capabilities reach well beyond the realm of the web; for example, it can be used to generate SQL, PostScript and XML from templates. It can be used either as a standalone utility for generating source code and reports, or as an integrated component of other systems.

```
VelocityEngine velocityEngine = new VelocityEngine();
velocityEngine.init();

Template t = velocityEngine.getTemplate("index.vm");

VelocityContext context = new VelocityContext();
context.put("name", "World");

StringWriter writer = new StringWriter();
t.merge( context, writer );

System.out.println(writer);
```
