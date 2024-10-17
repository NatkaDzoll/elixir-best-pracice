Manipulate with data:


Before:
```

users = [{1, "test_operator}, {2, "coingaming"}]
operator_options =
     users
      |> Enum.map(&{to_string(&1.id), &1.name})
      |> Enum.map(fn {key, value} -> {value, key} end)
      end
```

After:

```
users = [{1, "test_operator}, {2, "coingaming"}]
operator_options =
      for operator <- users do
        {operator.name, to_string(operator.id)}
      end
```



# elixir-best-pracice
