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

9. What is a meta-model constraint?
A meta-model constraint is an extra limitation that cannot be easily expressed within the meta-model itself and hence
is rather written in another language and then checked against a concrete instance of the meta-model.
