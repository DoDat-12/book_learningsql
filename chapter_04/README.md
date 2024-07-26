# Chapter 4. Filtering

## Condition Evaluation

A `WHERE` clause may contain one or more _conditions_, separated by the operators `AND` and `OR`

    WHERE first_name = 'STEVEN' AND create_date > '2006-01-01'

### Using Parentheses

    WHERE (first_name = 'STEVEN' OR last_name = 'YOUNG')
        AND create_date > '2006-01-01'

### Using the not Operator

    WHERE NOT (first_name = 'STEVEN' OR last_name = 'YOUNG') --NOT for this line--
        AND create_date > '2006-01-01'

- You can use the `not` operator:

    ```    
    WHERE first_name <> 'STEVEN' AND last_name <> 'YOUNG'
        AND create_date > '2006-01-01'
  
    /* first_name not equal 'STEVEN' */
    ```

## Building a Condition
A condition is made up of one or more expressions combined with one or more operators

An expression can be any of the following:
- A number
- A column in a table or view
- A string literal, such as `'Maple Street'`
- A build-in function, such as `concat('Learning', ' ', 'SQL')`
- A subquery
- A list of expressions, such as `('Boston', 'New York', 'Chicago')`

The operators used within conditions include:
- Comparison operators, such as `=`, `!=`, `<`, `>`, `<>`, `like`, `in`, and `between`
- Arithmetic operators, such as `+`, `-`, `*`, and `\`

## Condition Types
