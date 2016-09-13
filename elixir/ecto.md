# Ecto

## [https://hexdocs.pm/ecto/Ecto.html#build_assoc/3](build_assoc/3)

Example schema:
```elixir

defmodule Post do
  use Ecto.Schema

  schema "posts" do
    field :title
    field :body
    has_many :comments, Comment
    timestamps
  end
end

defmodule Comment do
  use Ecto.Schema

  schema "comments" do
    field :body
    belongs_to :post, Post
    timestamps
  end
end
```

Example usage:
```elixir
post = Repo.insert!(%Post{title: "hello", body: "world"})
comment = Ecto.build_assoc(post, :comments, body: "Excellent")

# above is equivalent to %Comment{post_id: post.id, body: "Excellent"}
```

