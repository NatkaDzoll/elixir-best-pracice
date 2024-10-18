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

@admin_statuses UserStatus.Utils.values()
                  |> Enum.filter(fn status -> status != :BANNED end)
                  |> Enum.map(&%{label: to_string(&1), value: to_string(&1)})
  @admin_statuses for s <- UserStatus.Utils.values(), s != :BANNED do
                    %{label: to_string(s), value: to_string(s)}
                  end


# elixir-best-pracice
