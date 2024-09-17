# Splunk

[Splunk Doc](https://docs.splunk.com/Documentation/Splunk/9.0.2/SearchReference/UnderstandingSPLsyntax)

* Self-hosted tool
* Used to retain, analyse and search an organisation's log data
* It has its query language: search Processing Language (SPL)
* SPL searches and retrieves events from indexes using the Splunk search and reporting app.

```html
index=main fail
```

* `index=main`&#x20;

Its the beginning of the search command

To retrieve events from index names 'main'&#x20;

index stores data that has been collected and processed by Splunk

* `fail`

to return any event that contains the term 'fail'



### Pipes ( | )

&#x20;Sends output of one command as the input to another command

```html
index=main fail | char count by host
```

retrieve events from an index named main for events containing the search term fail --> transform the search results by creating a chart acc to count or a number of events by Host.

### Wildcard

It matches characters in string values.

Help find events that contain data that is similar but not entirely identical.&#x20;

```html
index=main fail*
```

To search for all possible endings that contain the term fail, like failed or failure.





## Resources:

{% embed url="https://www.splunk.com/en_us/training/free-courses/overview.html" %}







