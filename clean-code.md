Naming convention 
1. Use intention revealing names e.g. customerList, activeCustomers, customers and not cList, acs, cs
2. avoid disinformation, avoid false clues e.g. hp - hp platform name or hypotenuse or high priority ?
3. Make meaningful distinctions; copyChars (char a1[], char a1[]) => copyChars(char source[]. char destination[]) 
 Avoid indistinct noise words e.g. ProductInfo, ProductData here Info and Data are indistinct noise words. Avoid using redundant noise words like variable, var, String, table in variable names. 
Other meaningless distinctions are # getAccount(), getAcocuntInfo() # money, moneyAmount # customerInfo, customer # theMessage, message these example offer no help to reader to distinguish its meaning.
1. Use pronounceable words programming is social activity when you discuss you would not like to spell “gen why emm dee aich emm ess” for genymdhms better to name as generationTimestamp; modymdhms => modificationTimestamp
Intelligent conversation is now possible: “Hey, Mikey, take a look at this record! The gen-
eration timestamp is set to tomorrow’s date! How can that be? also look at the modification timestamp is null always”


1. use searchable name to find across file in projects e.g. MAX_REQUEST_PER_THREAD is easy to find than hard coded value 10. Avoid single letter variable name except local scope like loop etc
2. Avoid type or scope encoding e.g. intCounter, localCounter. In modern languages like Java using encoding will mislead reader e.g. PhoneNumber phoneString; Avoid prefix encoding like m_ e.g. m_description = description instead use this.description = description. 
Exception to this is  interface & implementation, we need to encode names to differentiate the interface with implementation so IShapeFactory, ShapeFactory OR ShapeFactory, ShapeFactoryImp / CShapeFactory
        
1. Avoid mental mapping - Do not give opportunity to reader to translate name to what they already know. using single letter names (i,j,k) in loop are traditional but using a, b, c in other context should be avoided.
2. Class name should be noun e.g. Customer, Account, WikiPage etc. Avoid words like Manager, Processor, Data & Info i.e. verb should be avoided.
3. Method names should be verb or verb phrases like postPayment, deletePage, save. Accessor, mutator & predicate should be prefixed according to javabean standard e.g. getName, setName, isFlagged
4. When constructors are overloaded use static factory method with name describing the argument. And consider making corresponding constructor private to enforce use of factory method.
        e.g. point = Complex.fromRealNumber(2.3); -> private Complex(float ) {}
1. Avoid cute, funny names e.g. whack => kill, holyHandGranade => deleteItems etc
2. Pick one word for one abstract concept and stick with it. retrieve = fetch = get so if you are using get use it throughout the project. Other example controller = manager = driver 
3. Do not use same word for two purpose. e.g. add where at one location it's concatenating string at another location it's adding value to list. so make decision to choose add, append, insert etc. verbs appropriately.
4. Use solution domain name wherever required i.e. computer science terms like algorithm name, pattern name, math term formulas etc. mapping it to problem domain has down side that coworker would go back to customer asking what it is.
5. Use problem domain name - code that has more to do with problem domain concept should use domain name
6. Add meaningful context, few names are meaningful but those which are not we need to add context by adding prefix etc e.g. addrFirstName, addrLastName etc
7. Do not prefix each artifact with project acronym e.g. GSDCustomer, GSDAddress 
8. Choose names wisely in similar context e.g. PostalAddress, MAC, URI all are addresses using Address for postal address would create ambiguity.
9. Good naming requires good descriptive skills and shared cultural background.




Functions
1. Should be small - 150 chars long and 20~100 lines.
2. Blocks - control structure blocks should have 1~2 line and that be function call. Indent should be at level 1 or 2.
3. Function containing fetch, search, process, generate, print should be in split into smaller function “One thing at a time” so… getCustomers(), searchActiveCustomer(), updateProfile(), generateProfile(), printProfile() 
4. Larger function are sometime unavoidable divide them with declaration, initialization and logic part.
5. One level of abstraction - function to do one thing at a time make sure function are at same level of abstraction.
6. Use descriptive name even it becomes long.
7. Argument should be 0~2 become easy to understand and test. 1 arg is best.
8. Same variable / argument should not be passed and processed in multiple function.
9. Do not use out argument (pass by reference and use as output post processing) use return statement. e.g. void includeSetupPageInto(StringBuffer pageText) . Using an output argument instead of a return value for a transformation is confusing.
10.  Flag arguments should be avoided as they do two things and bit difficult to understand. e.g. printChart(true) what this true if for ? better create two functions printAdvanceChart(), printSimpleChart() use it like if (customer.hasSubscription()) printChartAdvance() else printSimpleChart()
11. Two argument function - arguments should be correlated / natural ordering e.g. copy(source, destination) Point(x, y). And should not be like writeField(stream, name) better create FieldWriter have stream as member initialize stream in constructor and fieldWriter.write(name); 
12.  Functions like assertEqual(expected, actual) are also problematic they are not in natural order; people tend to use actual in place of expected it requires practice to learn.
13. Three args / triads are difficult e.g. overloaded assertEquals(message, expected, actual) use only when necessary
14. Argument object - if arguments are part of concept or domain it make sense to create class / object and pass to function. makeCircle(Point p, double radius) instead of makeCircle(x, y, r)
15. Variable arg list - sometimes we need var args list, monad, dyad or triad are ok but more than that should be avoided.
16. Choose good name for function name. order and intent of argument is also important.In case of monad verb / noun pair is nice idea e.g. writeField(name) than write(name) 
17. Keyword form of function name - assertExpectedEqualsActual(expected, actual) gives better understanding of which is first argument that remembering it (assertEquals(e, a))
18. Have no side effect -  function should “do one thing”, unexpected changes, mistrust create problem. e.g. in function validateUser() function should only validate user, it should not initialize the session or print message on failure. If you want to have function like checkUserAndInitializeSession() 
19. Output argument should be avoided appendFooter(report); here footer is appended to report which should be avoided. Rather have return statement return report; in appendFooter or best option is to call on object itself report.appendFooter();
20. Command query separation - function should either do something/change state or return information should not do both. e.g. setName(name) { this.name = name; return true;} is wrong. Better have nameExists() and setName(name)
21. Prefer exception than returning code, else it will create deeply nested structure.
22. try catch block mix error processing with normal processing. It is better to have try block in different function. Allowing separation and easy to understand code.
        public void delete(Page page) {
try {
deletePageAndAllReferences(page);
}
catch (Exception e) {
logError(e);
}
}
private void deletePageAndAllReferences(Page page) throws Exception {
deletePage(page);
registry.deleteReference(page.name);
configKeys.deleteKey(page.name.makeKey());
}
private void logError(Exception e) {
logger.log(e.getMessage());
}


1. Error handling is one thing - if function is handling error it should do only that nothing else so first line of function is try and there should be nothing after catch / finally
2. Use exception class instead error codes. Programmer tend to use the enum class with error codes defined in it, downside is we need to recompile while project, when we add new error code. As recompilation is needed programmer tend to use existing error code resulting compromise in quality & harder to maintain code at later stage. 
3. Do not repeat yourself - avoid duplication (error in algo, exception handling, testability, reusability will automatically be taken care of)
4. 

Coding is art. Think yourself as writer, create a draft it may have duplication, improper name, nested, multi level structured, long functions etc. Revisit, refine and make it best.


Building software is like creating language for domain problem that describes the system as whole. Functions are verbs, classes are nouns. Reading code should be like a storytelling by programmer.


Comments
1. Code should be so easy, expressive and self explanatory such that there need be no comment. Comments mean failure.
2. Comment if not maintained becomes inaccurate, obsolete, misleading
3. I wrote bad code, confusing, disorganized so I should comment it well rather I should write clear, expressive code and spend energy in that.
4. Code is always a truth, comment may not be.
5. Legal comments are ok e.g. copyright, author details etc
6. Informative comments are ok e.g. commenting on abstract method, regexp
7. Comment about the decision / intent is OK e.g. Best attempt to create race condition for test
8. Clarification comments are OK (why it work that way)
9. Warning for consequences e.g. running test will take longer OR this is not thread safe
10.  TO DO comments are like reminders, future impl, problem areas but do not over do
11. Amplification - stress on why this is needed
12. API Docs comments OK if you are writing public API
13. Do not just write the comment because you have to follow process
14. Mandatory comments for variable, function, class creates the clutter in code and if not maintained becomes misinformation or lie
15. Journal comments - task/change comment in file being edited is not necessary as we nowadays uses version control system
16. Noise comment - obvious with no new info is noise e.g. //default constructor OR //class employee OR //Name of employee OR //return day of month 
17. Bad comments funny / sexy / casual comments
18. Do not write the comment / logic before coding.
19. Do not use position marker // ACTION
20. Closing brace comment // end for // end try // end while BAD
21. Do not use attribution and bylines e.g. added by aslam let git or else maintain it
22. Do not keep commented code for later use / delete etc let git or so do it
23. If you are using javadocs to generate API doc in HTML use it properly
24. Comment should have local contextual information not system wide info or details of implementation in other file
25. Do not write too much information in comment like 10 paras explaining algo
26. Do not discuss the term which is unrelated to context.


Formatting
1. Formatting is important. Formatting is about communication and first job of programmer.
2. Blank like provides visual cue about new section, group or concept.
3. Concept that are related should be kept vertically close. e.g. in function a b & c are called c calls function d; function definition in file should follow order as a, b , c , d
4. Variable declaration should be close to their usage. Control variable for loop be declared in loop.
5. Instance variable should be declared at one place generally at top.
6. Dependent function should be vertically close and orderly placed.
7. Concept  having strong affinity like doing same kind of task, sharing same name scheme, overloading should be vertically close. e.g. assertTrue(flag), assertTrue(flag, message), assertFalse(flag), assertFalse(flag, message) then logMessage(message) even logMessage is used in assertTrue(flag)
8. Horizontal - 120 chars per line is good option nowadays as screens are wide enough to hold.
9. Conjoin element should be without space, disjoin should have space e.g. public function sum(Integer x) {  , copyChars(source, destination), x = y;
10. Higher precedence (implicit or explicit) are conjoin b*c - 4*a*x;  (a+b) - (c*d)
11. Do not align variable, expression in same column line.
private    int          age;
public     String     name;
1. Source code is hierarchical document than outline. Indentation is the most important thing to make it readable.
2. Formatting, coding convention should be agreed upon and followed by team. All team member should use same preference or profile for formatting, possibly IDE as well.
3. 

Object and Data Structure
1. Hiding implementation is not just a matter of putting a layer of functions between the variables. Hiding implementation is about abstractions!
2. Procedural code makes easy to add new function without changing data structure. But if we add new data structure we need to change all functions. OO makes easy to add new classes but makes difficult to add new function as all classes need to change.
3. Law of demeter says module should not know the innards of object it manipulates i.e. function f of class C, can call functions of A, functions of object it creates locally, functions of member object of C, argument passed. Violation example - function f => final String outputDir = ctxt.getOptions().getScratchDir().getAbsolutePath(); here it gets Directory object that means it knows innards of object ctxt (The calling function knows how to navigate through a lot of different objects.)
4. Even if you have private member's bean specification says you should have accessor and mutators. Hence you tend to expose objects in the chain to outside world that's a problem as in above example. What are you hiding ?
        final String outputDir = ctxt.options.scratchDir.absolutePath; would have been fine because those members are public by law and there’s nothing to hide per specification.
1. Hiding structure - adding behavior helps to hide the structure. e.g. BufferedOutputStream bos = ctxt.createScratchFileStream(classFileName); Now context directly provides the required stream through bhavior.
2. DTO -  called a data transfer object, or DTO. DTOs are very useful struc-tures, especially when communicating with databases or parsing messages from sockets, and so on. They often become the first in a series of translation stages that convert raw data in a database into objects in the application code. The beans. It provide no benefit.
3. Active records -  are specialized DTOs with fetching, navigation & crud methods e.g. get, save, find etc. Do not add business rules in them.
4. Important expose behavior and hide data. This makes easy to add new classes without changing behavior.


Classes
1. Hiding implementation is not just a matter of putting a layer of functions between the variables. Hiding implementation is about abstractions!
2. 

Error Handling
1. Pending


Boundaries
1. Pending


Unit Tests
1. Write test like production code; neat, clean, well thought & designed. Because in future when they become thousands in numbers it would be difficult to understand if not maintained well. Thousand tests will make sure you have no bug in system.
2. Maintaining test helps to make change in code confidently. Breaking other part of system due to change is minimized.
3. Build-Operate-Check pattern - build test data, operate on test data and check expected result.
4. Domain specific language - create API for test e.g. build data, check results.
5. One assert per test or minimum, easy to understand & yields in creating your own DSL / API e.g. checkInvoiceState()
6. Single concept per test e.g. testAddPayment not testPayment containing add, edit or delete
7. FISRT rule - test should be Fast run quickly, Independent should have their own data and can run in order without any dependency, Repeatable should run in any environment e.g. production, QA, dev machines, Self-validating  should have boolean output and need not to write parsing, manual compare etc. assertTrue(file1.equals(file2)), Timely should be written before production code and not after writing production code.


Systems
1. Big design upfront is not necessary, but your code should be modular, decoupled to adopt future requirement.
2. POJO, DI should be used
3.
