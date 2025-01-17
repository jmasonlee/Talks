# From Chaos to Clarity

## Talk Resources
* [Slides](https://github.com/jmasonlee/Talks/blob/master/Slides/Chaos_to_clarity%20%5BAutosaved%5D.pptx.bak.pptx)

### Sample splunk dashboard with graph showing number of queries by a user each query date in splunk:
```
<form version="1.1">
  <label>Table Usage Counts</label>
  <description>Dashboard to display number of queries per date by a specific user</description>
  <fieldset submitButton="false">
    <input type="time" token="search_range">
      <label>date range</label>
      <default>
        <earliest>-7d@h</earliest>
        <latest>now</latest>
      </default>
    </input>
    <input type="text" token="table">
      <label>table name</label>
    </input>
    <input type="text" token="user_name">
      <label>user</label>
    </input>
  </fieldset>
  <row>
    <panel>
      <chart>
        <title>Searches per dt</title>
        <search>
          <query>index=<your index> (<your report with a query>) $table$ "*"
          | eval query_date=strftime(_time, "%Y-%m-%d")
          | eval user_name_filter="%$user_name$%"
          | where like(user_name, user_name_filter)
          | stats count by query_date
          <earliest>$search_range.earliest$</earliest>
          <latest>$search_range.latest$</latest>
        </search>
        <option name="charting.chart">line</option>
        <option name="charting.drilldown">none</option>
        <option name="refresh.display">progressbar</option>
      </chart>
    </panel>
  </row>
```

## Jacqueline's

* [Blog](http://jmasonlee.github.io/)
* [Calgary Software Crafters](https://www.meetup.com/Calgary-Software-Crafters/)

## Given At
  * 2025-01-17 [Calgary Software Crafters/Tech Connect Alberta](https://www.meetup.com/calgary-software-crafters/events/305468464/)
