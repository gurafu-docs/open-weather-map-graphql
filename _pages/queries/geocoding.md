---
title: Geocoding
permalink: /open-weather-map/queries/api/geocoding/
---

The `geocoding` field provides location-based services, including direct, reverse, and ZIP code lookup.

## Direct Geocoding

### Query

```graphql
query ($directInput: DirectInput) {
  api {
    geocoding {
      direct(input: $directInput) {
        name
        lat
        lon
        country
        state
        local_names {
          ascii
          feature_name
          ms
          gu
          is
          wa
          mg
          gl
          om
          ku
          tw
          mk
          ee
          fj
          gd
          ky
          yo
          zu
          bg
          tk
          co
          sh
          de
          kl
          bi
          km
          lt
          fi
          fy
          ba
          sc
          ja
          am
          sk
          mr
          es
          sq
          te
          br
          uz
          da
          sw
          fa
          sr
          cu
          ln
          na
          wo
          ig
          to
          ta
          mt
          ar
          su
          ab
          ps
          bm
          mi
          kn
          kv
          os
          bn
          li
          vi
          zh
          eo
          ha
          tt
          lb
          ce
          hu
          it
          tl
          pl
          sm
          en
          vo
          el
          sn
          fr
          cs
          io
          hi
          et
          pa
          av
          ko
          bh
          yi
          sa
          sl
          hr
          si
          so
          gn
          ay
          se
          sd
          af
          ga
          or
          ia
          ie
          ug
          nl
          gv
          qu
          be
          an
          fo
          hy
          nv
          bo
          id
          lv
          ca
          no
          nn
          ml
          my
          ne
          he
          cy
          lo
          jv
          sv
          mn
          tg
          kw
          cv
          az
          oc
          th
          ru
          ny
          bs
          st
          ro
          rm
          ff
          kk
          uk
          pt
          tr
          eu
          ht
          ka
          ur
        }
      }
    }
  }
}
```

### Variables

```json
{
  "directInput": { "q": "New York", "limit": 5 }
}
```

## Direct Geocoding

### Query

```graphql
query ($zipZip: String!) {
  api {
    geocoding {
      zip(zip: $zipZip) {
        zip
        name
        lat
        lon
        country
      }
    }
  }
}
```

### Variables

```json
{
  "zipZip": "10001"
}
```

## Reverse Geocoding

### Query

```graphql
query ($reverseInput: ReverseInput) {
  api {
    geocoding {
      reverse(input: $reverseInput) {
        name
        lat
        lon
        country
        local_names {
          ascii
          feature_name
          ms
          gu
          is
          wa
          mg
          gl
          om
          ku
          tw
          mk
          ee
          fj
          gd
          ky
          yo
          zu
          bg
          tk
          co
          sh
          de
          kl
          bi
          km
          lt
          fi
          fy
          ba
          sc
          ja
          am
          sk
          mr
          es
          sq
          te
          br
          uz
          da
          sw
          fa
          sr
          cu
          ln
          na
          wo
          ig
          to
          ta
          mt
          ar
          su
          ab
          ps
          bm
          mi
          kn
          kv
          os
          bn
          li
          vi
          zh
          eo
          ha
          tt
          lb
          ce
          hu
          it
          tl
          pl
          sm
          en
          vo
          el
          sn
          fr
          cs
          io
          hi
          et
          pa
          av
          ko
          bh
          yi
          sa
          sl
          hr
          si
          so
          gn
          ay
          se
          sd
          af
          ga
          or
          ia
          ie
          ug
          nl
          gv
          qu
          be
          an
          fo
          hy
          nv
          bo
          id
          lv
          ca
          no
          nn
          ml
          my
          ne
          he
          cy
          lo
          jv
          sv
          mn
          tg
          kw
          cv
          az
          oc
          th
          ru
          ny
          bs
          st
          ro
          rm
          ff
          kk
          uk
          pt
          tr
          eu
          ht
          ka
          ur
        }
        state
      }
    }
  }
}
```

### Variables

```json
{
  "reverseInput": { "lat": 40.748817, "lon": -73.985428, "limit": 5 }
}
```
