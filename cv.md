Sergey Berezhnoy
============
* Email:                            ya_sergey@yahoo.com
* Phone:                            +79180000000
* telegram                          BerezhnojSergej

Summary
----------
Hello. My name is Sergey. I am a junior front-end developer
I specialize in front-end and single page application development on Vue.js. I very like my profession

**My main goals:**

* Become a senior programmer

* Learn english

* Learn new approaches in developing


Skills
--------------------
**Programming Languages and frameworks:**
* Javascript
* HTML
* CSS
* VueJS
* NodeJS (Basic)

Code example
----------------------------------------
```javascript
actions: {
    GET_DISTANCE: async (context, payload) => {
      const { from, to } = payload;
      let data = {
        time: new Date().toLocaleString("ru"),
        direction: `${from} - ${to}`
      };
      try {
        const codes = await Promise.all([
          ymaps.geocode(from),
          ymaps.geocode(to)
        ]).then(values => {
          return values.map(item =>
            item.geoObjects.get(0).geometry.getCoordinates()
          );
        });
        const distance = await Math.round(
          ymaps.coordSystem.geo.getDistance(...codes) / 1000
        );
        data.distance = `${ distance } км`
      } catch (e) {
        data.distance = e.message;
      } finally {
        context.commit("SET_DISTANCE_LOG", data);
      }
    }
  }
```

Experience
---------

My list of projects: https://gitlab.com/skaarjz

Education
---------

2009-2014
:   **Kuban State Technological University**: Krasnodar

English
---------

Level: A2
