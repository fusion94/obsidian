# Continuous Delivery

![rw-book-cover](https://images-na.ssl-images-amazon.com/images/I/51yF2SYUi7L._SL200_.jpg)

## Metadata
- Author: [[Jez Humble, David Farley]]
- Full Title: Continuous Delivery
- Category: #books

## Highlights
- Speed is essential because there is an opportunity cost associated with not delivering software. You can only start to get a return on your investment once your software is released. ([Location 795](https://readwise.io/to_kindle?action=open&asin=B003YMNVC0&location=795))
    - Note: point 7
- • Automated. If the build, deploy, test, and release process is not automated, it is not repeatable. Every time it is done, it will be different, because of changes in the software, the configuration of the system, the environments, and the release process. Since the steps are manual, they are error-prone, and there is no way to review exactly what was done. This means there is no way to gain control over the release process, and hence to ensure high quality. Releasing software is too often an art; it should be an engineering discipline. • Frequent. If releases are frequent, the delta between releases will be small. This significantly reduces the risk associated with releasing and makes it much easier to roll back. Frequent releases also lead to faster feedback—indeed, they require it. Much of this book concentrates on getting feedback on changes to your application and its associated configuration (including its environment, deployment process, and data) as quickly as possible. ([Location 808](https://readwise.io/to_kindle?action=open&asin=B003YMNVC0&location=808))
    - Note: point 8
- A working software application can be usefully decomposed into four components: executable code, configuration, host environment, and data. ([Location 822](https://readwise.io/to_kindle?action=open&asin=B003YMNVC0&location=822))
    - Note: point 9
- They are as comprehensive as possible—that is to say, they cover more than 75% or so of the codebase, so that when they pass, we have a good level of confidence that the application works. ([Location 863](https://readwise.io/to_kindle?action=open&asin=B003YMNVC0&location=863))
    - Note: point 10
- You should start by looking at that part of your build, deploy, test, and release process that is currently the bottleneck. You can, and should, automate gradually over time. Keep Everything ([Location 1112](https://readwise.io/to_kindle?action=open&asin=B003YMNVC0&location=1112))
    - Note: point 11
- Defects are fixed most cheaply if they are never checked in to version control in the first place. ([Location 1140](https://readwise.io/to_kindle?action=open&asin=B003YMNVC0&location=1140))
    - Note: point 12
- An open source tool called ESCAPE [apvrEr] ([Location 1518](https://readwise.io/to_kindle?action=open&asin=B003YMNVC0&location=1518))
    - Note: escape
- It should always be cheaper to create a new environment than to repair an old one. ([Location 1633](https://readwise.io/to_kindle?action=open&asin=B003YMNVC0&location=1633))
    - Note: recreation cost
- • The various operating systems in your environment, including their versions, patch levels, and configuration settings • The additional software packages that need to be installed on each environment to support your application, including their versions and configuration • The networking topology required for your application to work • Any external services that your application depends upon, including their versions and configuration • Any data or other state that is present in them (for example, production databases) ([Location 1641](https://readwise.io/to_kindle?action=open&asin=B003YMNVC0&location=1641))
    - Note: configuration information
- Keep binary files independent from configuration information, and keep all configuration information in one place. ([Location 1648](https://readwise.io/to_kindle?action=open&asin=B003YMNVC0&location=1648))
    - Note: configuration storage
