### Demonstrate issue with rules_dotnet and WPF

Two unrelated targets; an exe and a lib, both using WPF and .NET Framework 4.8

Basically empty skeletons. One target uses Microsoft.Win32.Registry to demonstrate challenges we had building against that.

#### Visual Studio
Open .sln, build, run, see dialog

#### Bazel
bazel build //HelloWorld
bazel build //HelloWorldLib
