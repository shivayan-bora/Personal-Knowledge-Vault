
This is used to represent tabular data:

```html
<table>
    <!-- Table Heading -->
    <thead>
        <!-- Table Row -->
        <tr>
            <!-- Table Header -->
            <th>Col 1</th>
            <th>Col 2</th>
            <th>Col 3</th>
        </tr>
    </thead>
    <!-- Table Body -->
    <tbody>
        <tr>
            <!-- Table Data -->
            <td>col 1 data</td>
            <td>col 2 data</td>
            <td>col 3 data</td>
        </tr>
        <tr>
            <td>col 1 data</td>
            <td>col 2 data</td>
            <td>col 3 data</td>
        </tr>
        <tr>
            <td>col 1 data</td>
            <td>col 2 data</td>
            <td>col 3 data</td>
        </tr>
    </tbody>
</thead>
```

`colspan` can be used to specify how much space a column should take.
`rowspan` can be used to specify how much space a row should take.

Earlier, tables were used to create layouts. However, it's notoriously difficult to make that layout responsive. Hence, it's always best to use tables specifically for representing tabular data and handle responsiveness with CSS.
