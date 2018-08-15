# EmailReplyParser [![Build status](https://ci.appveyor.com/api/projects/status/egn8m4a0iqeq6ib0?svg=true)](https://ci.appveyor.com/project/jokokko/emailreplyparser) [![NuGet Version](http://img.shields.io/nuget/v/EmailReplyParser.svg?style=flat)](https://www.nuget.org/packages/EmailReplyParser/)
Email reply parser.

**Package** [EmailReplyParser](https://www.nuget.org/packages/EmailReplyParser) | **Platforms** .NET 4.6, .NET Standard 2.0

Quick .NET (C#) port of https://github.com/crisp-im/email-reply-parser with small amendments.

### Usage
```csharp
var email = EmailParser.Parse(emailContent);
// Amending the default header quote regex patterns with pattern for Outlook displaynames...
var otherEmail = EmailParser.Parse(otherEmail, RegexPatterns.QuoteHeadersRegex.Concat(new [] {new Regex( @"^\s*(From\s?:.+\s?(\[|\().+(\]|\)))", RegexOptions.Compiled)} ).ToArray());

foreach (var fragment in otherEmail.Fragments)
{
    Console.WriteLine(fragment.Content);
}
```

### Original credits

* GitHub
* William Durand <william.durand1@gmail.com>
* Crisp IM
