library(magick)
url <- "https://media.npr.org/assets/img/2017/09/14/gettyimages-10141026_slide-67be9fc1bca330b26debade87690b5e84286614d-s1100-c50.jpg"
meme <- image_read(url) %>% 
  image_scale(500)

one_text <- image_blank(width = 900, 
                          height = 900, 
                          color = "#000000") %>%
  image_annotate(text = "Statistics",
                 color = "#FFFFFF",
                 size = 90,
                 font = "Impact",
                 gravity = "center")
p1 <- c(meme, one_text) %>% 
  image_append()
image_write(meme, "my_meme.png")
