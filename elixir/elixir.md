# Elixir

## with

Used to chain pattern matches together. If any link in the chain fails to match,
the chain is aborted and the non-matching value is returned.

### Example:

Without `with`:
```elixir
case File.read(path) do
  {:ok, binary} ->
    case :beam_lib.chunks(binary, :abstract_code) do
      {:ok, data} ->
        {:ok, wrap(data)}
      error ->
        error
    end
  error ->
    error
end
```

Using `with`:
```elixir
with {:ok, binary} <- File.read(path),
		 {:ok, data} <- :beam_lib.chunks(binary, :abstract_code),
		 do: {:ok, wrap(data)}
```

[Reference](http://stackoverflow.com/questions/34210281/how-to-use-the-with-keyword-in-elixir-and-what-is-it-for)
