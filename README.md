# The birthday greetings kata in Kotlin 

A kotlin version of the [The birthday greetings kata](http://matteo.vaccari.name/blog/archives/154) created by [Matteo Vaccari](https://www.linkedin.com/in/matteovaccari/).

## Rules of the kata
write a program that

1. Loads a set of employee records from a flat file
1. Sends a greetings email to all employees whose birthday is today

The flat file is a sequence of records, separated by newlines; this are the first few lines:

```
last_name, first_name, date_of_birth, email
Doe, John, 1982/10/08, john.doe@foobar.com
Ann, Mary, 1975/09/11, mary.ann@foobar.com
```

The greetings email contains the following text:

```
Subject: Happy birthday!

Happy birthday, dear John!
```

with the first name of the employee substituted for “John”

The program should be invoked by a main program like this one:

```kotlin
fun main() {
    ...
    val birthdayService = BirthdayService(employeeRepository, emailService)
    birthdayService.sendGreetings(today())
}
```

Note that the collaborators of the birthdayService objects are injected in it. Ideally domain code should never create new objects.
