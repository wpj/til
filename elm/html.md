# HTML

## Transforming `msg`s

You can transform `msg`s produced by a block of `Html` to another `Msg` type
using `Html.map`:

```elm
type Msg = Left | Right

view : model -> Html Msg
view model =
  div []
    [ map (\_ -> Left) (viewButton "Left")
    , map (\_ -> Right) (viewButton "Right")
    ]

viewButton : String -> Html ()
viewButton name =
  button [ onClick () ] [ text name ]
```

The function passed as the first parameter to `Html.map` receives the original
`msg` and transforms it into the type of the param `Html msg` block. In the
above, `()` is mapped to either `Left` or `Right`.
