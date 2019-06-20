# Corretto 8

Amazon Corretto is a no-cost, multi-platform, production-ready distribution of the Open Java Development Kit (OpenJDK). The implementation is licensed under the GNU General Public License version 2 with a Classpath exception.

## Maintainers

* The Habitat Maintainers: <humans@habitat.sh>

## Type of Package

Binary package

## Usage

Install:
```
hab pkg install core/corretto8
```

Execute:
```
hab pkg exec core/corretto8 java -h
```

Add to a plan:
```
pkg_deps=(
  core/corretto8
)
```
## Note about JRE in this release.

Amazon Corretto 8 comes with JRE built in. To set the JRE_HOME if needed, do one of the following.(This package should set your JAVA_HOME by default on windows)
```
Windows:
```
function Invoke-SetupEnvironment {
  Set-RunTimeEnv JRE_HOME "$(Get-HabPackagePath corretto8)\jre"
}
```

In another function
```
$env:JRE_HOME =  "$(Get-HabPackagePath corretto8)\jre"
```
To test on windows
```
hab pkg install core/corretto8
```
hab pkg exec core/corretto8 java.exe -v
```
Add to your plan
```
$pkg_deps("core/corretto8")
```
