# Customising Packages

When I was working on my Goodreads Companion app, due to the way GR had implemented authorisation on their site I had to make changes to the oauth1 package on pub.dev.

I found this article explaining how to do it:

{% embed url="https://medium.com/flutter-community/how-to-modify-an-existing-pub-package-to-use-in-your-flutter-project-4e909452ee66" %}

In summary:

* Fork the repo of the package
* Clone the repo 
* Make your changes and push
* Add something like the following to your pubspec

```text
dependencies:
  flutter:
    sdk: flutter

  [package-name]:
    git:
      url: https://github.com/[git-username]/[git-repository-name]
```



