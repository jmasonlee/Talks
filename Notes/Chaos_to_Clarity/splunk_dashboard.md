# Splunk
![Screenshot 2025-01-17 at 3 03 53 PM](https://github.com/user-attachments/assets/e3ee17b7-1cd8-40ae-ab64-9e6fe9cf02c6)
### Query
Here is a sample query to find the number of queries running on a table each day
```spl
index=<your index> (<your report with a query>) <table name> "*"
          | eval query_date=strftime(_time, "%Y-%m-%d")
          | eval user_name_filter="%<the user name you want to see activity for>%"
          | where like(user_name, user_name_filter)
          | stats count by query_date
```
### Dashboard
This dashboard (which is not Yelp code) will let you re-use the above query for any combination of user name and table name, and show the results as a graph.
```xml
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
