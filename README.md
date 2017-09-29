
# PIT-library

This project aims at using pit inside a java project, without maven.

### Reproduction

First, compile the project target (from the root):

```
cd src/test/resources/test-projects
mvn test
```

Then, run the test of the project **PIT-Library** (from the root):

```
mvn test
```

You can fin the mutation analysis done by PIT in `mutations.csv`, obtained with:

```
mvn org.pitest:pitest-maven:mutationCoverage -DreportDirectory=out -DtargetClasses="example.*" -Dmutators=ALL -Dformat=CSV -DtargetTests=example.TestSuiteExample -DoutputFormats=CSV
```

Excerpt of the output:

```
8:15:04 AM PIT >> INFO : MINION : 8:15:04 AM PIT >> INFO : Found  6 tests

8:15:04 AM PIT >> INFO : MINION : 8:15:04 AM PIT >> INFO : Dependency analysis reduced number of potential tests by 0

8:15:04 AM PIT >> INFO : MINION : 8:15:04 AM PIT >> INFO : 6 tests received

8:15:04 AM PIT >> INFO : MINION : 8:15:04 AM PIT >> FINE : Running 6 units

8:15:04 AM PIT >> INFO : MINION : 8:15:04 AM PIT >> FINE : Gathering coverage for test Description [testClass=example.TestSuiteExample, name=test2(example.TestSuiteExample)]

8:15:04 AM PIT >> INFO : MINION : 8:15:04 AM PIT >> FINE : Gathering coverage for test Description [testClass=example.TestSuiteExample, name=test3(example.TestSuiteExample)]

8:15:04 AM PIT >> INFO : MINION : 8:15:04 AM PIT >> FINE : Gathering coverage for test Description [testClass=example.TestSuiteExample, name=test4(example.TestSuiteExample)]

8:15:04 AM PIT >> INFO : MINION : 8:15:04 AM PIT >> FINE : Gathering coverage for test Description [testClass=example.TestSuiteExample, name=test7(example.TestSuiteExample)]

8:15:04 AM PIT >> INFO : MINION : 8:15:04 AM PIT >> FINE : Gathering coverage for test Description [testClass=example.TestSuiteExample, name=test8(example.TestSuiteExample)]

8:15:04 AM PIT >> INFO : MINION : 8:15:04 AM PIT >> FINE : Gathering coverage for test Description [testClass=example.TestSuiteExample, name=test9(example.TestSuiteExample)]

8:15:04 AM PIT >> FINE : Coverage generator Minion exited ok
8:15:04 AM PIT >> INFO : Calculated coverage in 0 seconds.
8:15:04 AM PIT >> FINE : Used memory after coverage calculation 33 mb
8:15:04 AM PIT >> FINE : Free Memory after coverage calculation 116 mb
8:15:04 AM PIT >> FINE : According to coverage no tests hit the mutation MutationDetails [id=MutationIdentifier [location=Location [clazz=example.Example, method=charAt, methodDesc=(Ljava/lang/String;I)C], indexes=[4], mutator=org.pitest.mutationtest.engine.gregor.mutators.RemoveConditionalMutator_ORDER_ELSE], filename=Example.java, block=0, lineNumber=12, description=removed conditional - replaced comparison check with false, testsInOrder=[], isInFinallyBlock=false, poison=NORMAL]
8:15:04 AM PIT >> FINE : According to coverage no tests hit the mutation MutationDetails [id=MutationIdentifier [location=Location [clazz=example.Example, method=charAt, methodDesc=(Ljava/lang/String;I)C], indexes=[4], mutator=org.pitest.mutationtest.engine.gregor.mutators.RemoveConditionalMutator_ORDER_IF], filename=Example.java, block=0, lineNumber=12, description=removed conditional - replaced comparison check with true, testsInOrder=[], isInFinallyBlock=false, poison=NORMAL]
```