
To use gradle to build/run the hello-samza project:

1) if you don't have any version of gradle already installed, then install gradle - see the 'Install Gradle' section of: https://spring.io/guides/gs/gradle/

2) run the wrapper task to add gradle 2.3 to the hello-samza tree (assumes gradle executable is in your path)

	$ cd hello-samza
	$ gradle wrapper

3) download/install yarn/kafka/zookeeper:

	$ ./gradlew instGrid

4) build hello-samza project:

	$ ./gradlew distTar

5) deploy hello-samza project to grid:

	$ ./gradlew instTar

6) run the grid (starts up yarn/kafka/zookeeper):

	$ ./gradlew runGrid

7) run the various Samza tasks that are part of hello-samza project:

	$ ./gradlew runWikiFeed
	$ ./gradlew runWikiParser
	$ ./gradlew runWikiStats

8) view all the current Kafka topics:

	$ ./gradlew listKafka

9) view the Kafka topics output by the various Samza tasks:

	$ ./gradlew dumpWikiRaw
	( output of Kafka topic scrolls by)
	CTRL-c

	$ ./gradlew dumpWikiEdits
	( output of Kafka topic scrolls by)
	CTRL-c

	$ ./gradlew dumpWikiStats
	( output of Kafka topic scrolls by)
	CTRL-c

10) stop all the components:

	$ ./gradlew stopGrid

Shortcut: using the 'runWiki*' tasks directly will do steps 3-6 automatically.


