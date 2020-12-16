# Heroku JProfiler Buildpack

This buildpack will add the shared library to be used as the JProfiler agent to be loaded by the JVM. This allows
JProfiler to be used to profile the Java application running on Heroku.

## Usage

Add buildpack:

```
$ heroku buildpacks:add https://github.com/ignitionworks/heroku-jprofiler-buildpack --app YOUR_APP
```

Modify your JAVA_OPTS to include:

```
-agentpath:libjprofilerti.so=port=8849,nowait
```

See [JProfiler docs](https://www.ej-technologies.com/resources/jprofiler/help/doc/main/profiling.html) for more details.

Forward the port:

```
$ heroku ps:forward 8849 --app YOUR_APP
```

Then connect JProfiler
