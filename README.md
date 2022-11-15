# issue-2000-example
A minimal example reproducing https://github.com/eclipse/xtext-core/issues/2000

After cloning, run

```
mvn -f io.github.lorenzobettini.tychotestlanguage.parent clean verify -Dmaven.repo.local=$HOME/tmp/maven-repo
```

So that it will start from an empty .m2 cache folder.

When getting to `exec-maven-plugin` you should get:

```
0    [org.eclipse.emf.mwe2.launch.runtime.Mwe2Launcher.main()] ERROR mf.mwe2.launch.runtime.Mwe2Launcher  - IS_OSGI_RUNNING
java.lang.NoSuchFieldError: IS_OSGI_RUNNING
	at org.eclipse.emf.ecore.impl.EPackageRegistryImpl.createGlobalRegistry(EPackageRegistryImpl.java:55)
	at org.eclipse.emf.ecore.EPackage$Registry.<clinit>(EPackage.java:75)
	at org.eclipse.emf.mwe2.language.Mwe2StandaloneSetupGenerated.createInjectorAndDoEMFRegistration(Mwe2StandaloneSetupGenerated.java:38)
	at org.eclipse.emf.mwe2.launch.runtime.Mwe2Launcher.run(Mwe2Launcher.java:75)
	at org.eclipse.emf.mwe2.launch.runtime.Mwe2Launcher.main(Mwe2Launcher.java:36)
	at org.codehaus.mojo.exec.ExecJavaMojo$1.run(ExecJavaMojo.java:254)
	at java.base/java.lang.Thread.run(Thread.java:833)
```
