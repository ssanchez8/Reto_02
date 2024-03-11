## Reto_02
Reto 02-Programación Orientada a Objetos

El problema a modelar fue la interacción entre un usuario y un buscador de contenido digital, que permitiese seleccionar entre contenido como música, podcasts y videos cortos. Las clases que definen a cada tipo de contenido, heredan métodos de otra clase Multimedia que permite reproducir, parar, pausar o descargar el contenido. La interacción con el usuario se da mediante una solicitud de un string donde digite el contenido que quiere ver. 
```mermaid
classDiagram
    direction RL
    class User {
        +String nickname
        +int age
        +String gender
        +String nationality
        +Type_Selection()
    }

    class SearchEngine {
        + search_for(query: string) Result[]
    }

    class Result {
        +String title
        +String type
    }

    class Multimedia {
        +play()
        +pause()
        +stop()
        +download()
    }

    class Song {
        +String title
        +String artist
        +String language
        +String duration
        +String genre
    }

    class Genre {
        +String BPM
        +String instruments
        +String harmony
    }

    class Podcast  {
        +String title
        +String author
        +String duration
        +String description
        +String category
        +String publicationDate
    }

    class ShortVideo {
        +String title
        +String creator
        +String duration
        +String description
        +String tags
        +String publicationDate
    }
 
 direction TB
    User --> SearchEngine: selects
    SearchEngine --> Result

    Result --* Song 
    Result --* Podcast
    Result --* ShortVideo
    Song --* Genre

    Podcast --|> Multimedia
     Song --|> Multimedia
      ShortVideo --|> Multimedia

```
