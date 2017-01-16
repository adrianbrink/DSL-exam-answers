# Notes
- difference between .ecore, .genmodel and .aird
   - http://www.vogella.com/tutorials/EclipseEMF/article.html

# Exam Questions

1. Explain the advantages and disadvantages of implementing model-to-text transformations in Java vs. Xtend.
**Java**
+ already familar language
- no easy way to do multi-line string interpolation
- unable to mix control flow into templates

**Xtend**
+ enables easy string templating with Xpand
+ compiles to Java source code
- requires another language and hence increases complexity

Generally it is purely down to preference. Xtend might offer more inbuild functionality and helpful constructs
for M2T transformations, but it adds an extra layer of code generation and hence complexity.

2. Explain advantages and disadvantages of implementing model-to-model transformations in Java vs. Xtend.
**Java**
+ already familar language
+ able to load the meta-models since they have Java implementations

**Xtend**
+ specifically designed for M2M transformations
+ extends Java with useful functional-programming concepts
- new language

Generally it is purely down to preference. Xtend is Java just more modern and with helpers around M2M transformations.
In the end it is an arbitrary choice, whether you want to learn Xtend or not.

3. Explain in detail a diagram from your hand-in.

4. What is meta-modelling? What meta-modelling languages do you know?
A metamodel is a model of a model. It comes from the greek word 'meta' which means 'about'. 
A metamodel describes the abstract syntax.
- ecore, which is an implementation of MOF (Meta Object Facility)
- uml

5. Summarize differences between M2M and M2T transformations.
M2M transformation can either be edogenous (translates instances of a language to instances of the same language) or exogenous (translates 
instances of one language into instances of another language). M2M transformations are often used in pipeline approaches, where they allow
to desugar constructs, refactoring of code and models or computing values of expressions by reductions. M2T transformations are used
to generate output, such as an HTML text, SQL query, graphical description, ... .

6. What are applications of model transformation tools? What are the application of M2T? What are the applications of M2M?
Model transformation tools are used to generate Java implementations from ecore models. That is an instance of M2T transformation.
We use M2M transformations to expand the BinaryGenerators to an instance of a tree.

7. Are the instances used for testing in your project representative?
Yes for the generators. We could have used better test instances for our simple tree structures.

8. Why are you not using your ecore model in your Xtend program?
We are using our ecore model in our transformations.

9. What is ecore? What is the relation to MOF? what is its relation with UML?
Ecore is a meta modelling language which is the basis of the Eclipse Modelling Framework. Ecore itself is an implementation of MOF
(Meta Object Facility), which is a simple class diagramming language standardized by OMG. MOF is used to define the abstract syntax
of UML languages.

10. What is a meta-model constraint?
A meta-model constraint is an extra limitation that cannot be easily expressed within the meta-model itself and hence
is rather written in another language and then checked against a concrete instance of the meta-model.

11. Can you explain the meta-modelling hierarchy?
The meta-modelling hierarchy describes the different levels of abstraction. For example in the case of Ecore the M3 level
is the ecore language whcih allows to describe class diagrams. Instances of that language of class diagram at level 2. 
Level M1 has concrete models in the mind-map language and M0 contains real world objects. M0 is the least abstract level (or reality)
and M3 is the most abstract level.

12. What does M3 mean?
It is a description of the meta-modelling language itself that was designed after having created the language in the
language itself.

13. What is a DSL?
A DSL is a language that is very close to its domain so that it allows the users to work very close to their domain,
instead of through a lot of layers of abstraction. As an example, it is possible to specify trees in assembly code,
however through our DSL it is much simpler to do it, as the main focal point of the language is trees.

14. What is the difference between using DSLs and using feature models?
DSLs and feature models are two different techniques that belong to the same continuum of modeling domains. DSLs allow a
lot of freedom and flexibility, but are harder to maintain than FM. FMs are less expressive than DSLs and their configuration
options are typically more rigid. Yet, they require no meta-modelling and no concrete syntax.

15. Is the language you propose in your report a DSL? What is the domain it targets?
Yes, it targets easy specification of tree structures.

16. What is an internal (embedded) DSL? What is an external DSL? What implementation techniques do you know for implementing
internal/external DSLs?
An internal DSL is a library within a host language. It is cheap to implement, since all the tools from the host can be reused.
However it limits the control over syntax, semantics and tooling. Rails Active Record is an example.
An external DSL is a separate language, that is either parsed or interpreted. It gives you good control over syntax,
semantics and tooling. However it is costlier to implement. Google protocol buffers are an example.

17. ...

18. What is the key rationale for this work?
We were frustrated with how hard it is to generate complex tree structures for papers and hence wanted an easy way to specify them.
Of course, there exist similar approaches in LaTex already, however it was a good learning exercise and I think ours will become
more useful to us than LaTex.

19. What languages/tools can you indicate that can be used for implementing internal/embedded DSLs? What are the advantages of
implementing a DSL internally?
Parser combinator libraries which can be found in most standard libraries for most languages. A solid understanding of your host
language.
The advantages are that it is cheaper, faster and a lot of the tooling can be reused from the host language.

20. What is the difference between M2M and M2T transformation?
M2M transformations are either between the same class or between different types of classes. However, they produce the model
in another instance. M2T on the other hand produce strings.

21. Can you give examples of successful domain specific languages?
Ruby on Rails Active Record, Sinatra, OpenCL, Cuda, R, Octave, MatLab

22. What is a general purpose language (GPL)? How does it differ from a DSL?
A GPL is broadly applicable across domains whereas a DSL is only applicable to a specific domain,
such as statistics with R.

23. What is a product line architecture?
A product line architecture specifies the variable and the common parts to build multiple products
only differ in small parts of their code.
A software product line is a set of software-intensive systems that share a common, managed set
of features satisfying the specific needs of a particular market segment or mission and that 
are developend from a common set of core assets in a prescribed way.

24. What is the most common application scenario for Model Driven Development?
...

25. What is Xtext? What is its use case?
Xtext is a language framework bench that integrates

26. Describe the process of implementing a DSL using Xtext.
Create the .ecore file with meta-model
Create the default generator model for the ecore model
Generate model code
Create Xtext project from existing ecore models using the genmodel
Genreate Xtext code (grammar)
Run the DSL editing environment
Iteratively revise the grammar

27. What is variability modelling?
It is the modelling of the parts that will vary between different products from the same SPL.

28. What tasks are left to complete your project?
Refine the frontends more.
Add more frontends.
Add more testing to the M2T generators.

29. Please draw on the whiteboard classes representing the core concepts in your model and 
the relations between them.
....

30. Have you used automated testing in your project?
Yes, we have written testcases for legal and illegal instances of the model plus we have unit tests
the generators.

31. What is the difference between a conformance relation and inheritance relation in class models?
...

32. What is aggregation (composition)?
It means that one class contains the other class. E.g.: A car class would contain a list of wheels.

33. What is abstract syntax? What is concrete syntax? How do we specify abstract syntax of a
language? How do we specify concrete syntax?
Abstract syntax is what the meta-model describes.
Concrete syntax is what the end-user writes.
We use ecore and create meta-models that describe our abstract syntax.
We specify concrete syntax through the grammar of our language.

34. What is Eclipse Modelling Framework? What can it offer to software developers? How did you
use EMF in your project?
EMF is an Eclipse-based modelling framework and code generation facility for building tools and
other applications based in a structured data model.
It offers the developer tools such as ecore that allow one to specify the abstract syntax
of a language, generate Java classes from that as well as a grammar file which then can be used
to refine and extend the language. Furthermore it provides editors for the generated languages.
We used EMF extensively as our language workbench.

35. What is a left-recursive grammar? Did you have a problem with it in your project? What
is left-factorization of the grammar?
A left recursive grammar is one where a non-terminal symbol appears on the left and also as the 
first item on the right of the grammar. 
We didn't have a problem with it in our project since we prefixed all non-terminals and
terminals and hence we had no left recursion. 
http://www.csd.uwo.ca/~moreno//CS447/Lectures/Syntax.html/node8.html
Left-factorization no idea, we never mentioned it in the course.