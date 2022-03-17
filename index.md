![my_meme](https://user-images.githubusercontent.com/101034780/158909782-689d3138-209f-4988-97ce-e910dfa4d3c0.png)

# **Motivation**
I wrote this code during the very last few days before the assignment due date, so this meme is perfectly talking about what my feelings doing the assignment. This meme is an adaption of the stats220 lab.

## *code*
```{r}
library(magick)

#square one
party <- image_read("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTDxuYdPddIGu6kwWtbGHw6L6tjjqMcMhUe8Q&usqp=CAU") %>%
  image_scale(500)

#square two
party_text <- image_blank(width = 500,
                          height = 500,
                          color = "black") %>%
  image_annotate(text = "still a week\nbefore ddl",
                 color = "white",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

#square three
hardworking <- image_read("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQd1XUWLtVSyo1qZLACh1VQb3EfkJUgJubJbQ&usqp=CAU") %>%
  image_scale(500)

#square four
work_text <- image_blank(width = 500,
                         height = 500, 
                         color = "red") %>%
  image_annotate(text = "the last day\nbefore ddl",
                 color = "white",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

#making each row
top_row <- image_append(c(party, party_text))
bot_row <- image_append(c(hardworking, work_text))

c(top_row, bot_row) %>%
  image_append(stack = TRUE) %>%
  image_scale(800)

meme<- image_read("http://localhost:21322/session/preview.jpeg?viewer_pane=1&capabilities=1&host=http%3A%2F%2F127.0.0.1%3A39681")
image_write(meme, "my_meme.png")
```

