Manipulate with data:

```

operator_options =
      Utils.fetch_operators(auth)
      |> Enum.map(&{to_string(&1.id), &1.name})
      |> Enum.map(fn {key, value} -> {value, key} end)
    operator_options =
      for operator <- Utils.fetch_operators(auth) do
        {operator.name, to_string(operator.id)}
      end
```





# elixir-best-pracice
