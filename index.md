<html>
<body>

{% assign binderhub = site.data.index.entries.binderhub | sort: 'created' | reverse %}


<table>
  <tr>
    <th>release</th>
    <th>date</th>
  </tr>
  {% for chart in binderhub %}
    <tr>
      <td>
        <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version | remove_first: "v" }}
        </a>
      </td>
      <td>
        <span class='date'>{{ chart.created | date_to_rfc822 }}</span>
      </td>
    </tr>
  {% endfor %}
</table>


</body>
</html>
