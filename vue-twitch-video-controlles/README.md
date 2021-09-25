![Reda Ennakouri](https://raw.githubusercontent.com/redaEnnakouri/vue-twitch-video-controls/main/images/royalCode.jpeg)

# Package vue-twitch-video-controls
the objective of this package is to embed video twitch  with use all controls in Vue js

# GitHub
Link of the package at GitHub : https://github.com/redaEnnakouri/vue-twitch-video-controls

# Install package
install package with commande `npm i vue-twitch-video-controlls`

# Import Component 

```
<template>
    <vue-twitch-video-controlles />
</template>
   
   <script>
import VueTwitchVideoControlles from "@/vue-twitch-video-controlles.vue";

export defiault {
  components: {
    VueTwitchVideoControlles,
  }
};
</script>
```

# Video Control
For control video you need to send props to component like :

* video :String (you need to import id video at twitch)
* width :String
* height :String
* mute :Boolean
* autoplay :Boolean
* controls :Boolean (show controls video)
* allowfullscreen :Boolean

For Exemple :
``` 
<template>
     <vue-twitch-video-controlles
      :video="1148356867"
      :controls="true"
      :mute="false"
    />
</template>
   
   <script>
import VueTwitchVideoControlles from "@/vue-twitch-video-controlles.vue";

export defiault {
  components: {
    VueTwitchVideoControlles,
  }
};
</script>
```

# Buttons Controls
for hide buttons Controls you can send props `:allowButtons =false`

```
<template>
     <vue-twitch-video-controlles
      :video="1148356867"
      :allowButtons =false
    />
</template>
   
   <script>
import VueTwitchVideoControlles from "@/vue-twitch-video-controlles.vue";

export defiault {
  components: {
    VueTwitchVideoControlles,
  }
};
</script>
```

# Result 

![Result](https://raw.githubusercontent.com/redaEnnakouri/vue-twitch-video-controls/main/images/videoTwitch.png)








