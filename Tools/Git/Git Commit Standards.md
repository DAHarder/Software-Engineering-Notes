![[Pasted image 20230126163216.png]]


1. Commits MUST be prefixed with a type, which consists of a noun, feat, fix, etc., followed by a colon and a space.  
     
2.  The type feat MUST be used when a commit adds a new feature to your application or library.  
     
3.  The type fix MUST be used when a commit represents a bug fix for your application.  
     
4.  An optional scope MAY be provided after a type. A scope is a phrase describing a section of the codebase enclosed in parenthesis, e.g., fix(parser):
   
5. A description MUST immediately follow the type/scope prefix. The description is a short description of the code changes, e.g., fix: array parsing issue when multiple spaces were contained in string.

6.  A longer commit body MAY be provided after the short description, providing additional contextual information about the code changes. The body MUST begin one blank line after the description.

7.  A footer MAY be provided one blank line after the body. The footer SHOULD contain additional issue references about the code changes (such as the issues it fixes, e.g., Fixes #13).

8.  Breaking changes MUST be indicated at the very beginning of the footer or body section of a commit. A breaking change MUST consist of the uppercase text BREAKING CHANGE, followed by a colon and a space.

9.  A description MUST be provided after the BREAKING CHANGE:, describing what has changed about the API, e.g., BREAKING CHANGE: environment variables now take precedence over config files.

10.  The footer MUST only contain BREAKING CHANGE, external links, issue references, and other meta-information.

11.  Types other than feat and fix MAY be used in your commit messages.