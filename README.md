# go-halo5-api
go-halo5-api is a wrapper around the Halo5 API as documented at https://developer.haloapi.com.

# Usage
Set your API key as an environment variable.  Request and API key at https://developer.haloapi.com/products
```go
export HALO_API_KEY="123456789abcdefghi"
```
Import the halo package
```go
import "github.com/tbenz9/go-halo5-api/halo"
```
Start making API calls using the built in functions!

# Examples
Retrieve metadata about Halo5 vehicles
```go
package main

import (
    "fmt"
    "github.com/tbenz9/go-halo5-api/halo"
)

func main() {
    fmt.Println(string(Vehicles("https://www.haloapi.com", "h5")))
}
```
Results:
```go
{
    "name": "Scorpion",
    "description": "Main battle tank armed with a heavy cannon and pintle-mounted heavy machine gun. This new iteration of the storied Scorpion is half the mass of the old M808 yet has nearly identical firepower and armor protection.",
    "largeIconImageUrl": "https://content.halocdn.com/media/Default/games/halo-5-guardians/tools-of-destruction/vehicles/scorpion-6c7fb074aa1c42549a765a294e78c3c7.png",
    "smallIconImageUrl": "https://image.halocdn.com:443/?path=https%3a%2f%2fcontent.halocdn.com%2fmedia%2fDefault%2fgames%2fhalo-5-guardians%2ftools-of-destruction%2fvehicles%2fscorpion-6c7fb074aa1c42549a765a294e78c3c7.png&width=332&hash=%2fCkx7J14PgzU9QjJ5ndSwhhMk0%2bTZa6nlpEndWfyTHc%3d",
    "isUsableByPlayer": true,
    "id": "1730553442",
    "contentId": "c7e2f6aa-b86c-4131-b5d7-71bb35fcd0c4"
  },
  {
    "name": "Phaeton",
    "description": null,
    "largeIconImageUrl": "https://content.halocdn.com/media/Default/games/halo-5-guardians/tools-of-destruction/vehicles/vtol-5c02f48bfdf246c0aab7f738687b5744.png",
    "smallIconImageUrl": "https://image.halocdn.com:443/?path=https%3a%2f%2fcontent.halocdn.com%2fmedia%2fDefault%2fgames%2fhalo-5-guardians%2ftools-of-destruction%2fvehicles%2fvtol-5c02f48bfdf246c0aab7f738687b5744.png&width=332&hash=p%2b56GNOiSUDlhjfn%2ffB2d457Le7Vdw752wer9fGX0Ts%3d",
    "isUsableByPlayer": true,
    "id": "3394982816",
    "contentId": "011cd325-c192-477c-8767-23b99546031d"
  },
  {
    "name": "Mantis",
    "description": "Combat walker armed with heavy machine gun and missile launcher. Missiles can lock-on to aerial targets. Melee unleashes a devastating stomp attack. Extended use of the heavy machine gun will cause it to overheat.",
    "largeIconImageUrl": "https://content.halocdn.com/media/Default/games/halo-5-guardians/tools-of-destruction/vehicles/mantis-88bcd6e59a3d469aa380620309a5e8a5.png",
    "smallIconImageUrl": "https://image.halocdn.com:443/?path=https%3a%2f%2fcontent.halocdn.com%2fmedia%2fDefault%2fgames%2fhalo-5-guardians%2ftools-of-destruction%2fvehicles%2fmantis-88bcd6e59a3d469aa380620309a5e8a5.png&width=332&hash=bQ58hOrEtc%2b3XuXpGvrmzK31OhA5Ctt8mUlqXZ%2bMmRU%3d",
    "isUsableByPlayer": true,
    "id": "3227919741",
    "contentId": "71347094-6fdb-437a-862c-59db1b936aa6"
  },
  {
    "name": "Banshee",
    "description": "Agile ground attack aircraft. Armed with rapid-fire plasma cannons and secondary fuel rod cannon. Can perform acrobatic rolls and loops or high-speed boosts.",
    "largeIconImageUrl": "https://content.halocdn.com/media/Default/games/halo-5-guardians/tools-of-destruction/vehicles/banshee-9626ac8f343644f3a592a0b7d49faac6.png",
    "smallIconImageUrl": "https://image.halocdn.com:443/?path=https%3a%2f%2fcontent.halocdn.com%2fmedia%2fDefault%2fgames%2fhalo-5-guardians%2ftools-of-destruction%2fvehicles%2fbanshee-9626ac8f343644f3a592a0b7d49faac6.png&width=332&hash=%2bwTKTSuyqU6fPV%2f0JYmjU2YOh4SvpWEcKMVyHF7gL3U%3d",
    "isUsableByPlayer": true,
    "id": "419783896",
    "contentId": "91fafc39-ee57-4ae7-ad93-b36e6ac34561"
  },
  {
    "name": "Wraith",
    "description": "Assault tank armed with a heavy plasma mortar and pintle-mounted plasma cannon. Can boost for quick sprints. The latest Wraith revisits an ancient Sangheili design that is easier to manufacture and less costly to lose.",
    "largeIconImageUrl": "https://content.halocdn.com/media/Default/games/halo-5-guardians/tools-of-destruction/vehicles/wraith-bd8975a1a57348a2b8a2588e9a5040f1.png",
    "smallIconImageUrl": "https://image.halocdn.com:443/?path=https%3a%2f%2fcontent.halocdn.com%2fmedia%2fDefault%2fgames%2fhalo-5-guardians%2ftools-of-destruction%2fvehicles%2fwraith-bd8975a1a57348a2b8a2588e9a5040f1.png&width=332&hash=vr34Tpz64SEzQReJpo2bu0kn5bBSbyOGwpDwCXhzF0M%3d",
    "isUsableByPlayer": true,
    "id": "1206711506",
    "contentId": "c12685a5-956c-483b-8254-70765a23d863"
  },
  {
    "name": "Warthog",
    "description": "Warthog armed reconnaissance configuration fitted with a rotary autocannon on a full-rotation turret mount. ",
    "largeIconImageUrl": "https://content.halocdn.com/media/Default/games/halo-5-guardians/tools-of-destruction/vehicles/warthog-951f2406dea44d229662df881d89272e.png",
    "smallIconImageUrl": "https://image.halocdn.com:443/?path=https%3a%2f%2fcontent.halocdn.com%2fmedia%2fDefault%2fgames%2fhalo-5-guardians%2ftools-of-destruction%2fvehicles%2fwarthog-951f2406dea44d229662df881d89272e.png&width=332&hash=fgVOMTjIBBWxAMSe5%2bGu6VRwzTrdizeFN7F6YDNtbMw%3d",
    "isUsableByPlayer": true,
    "id": "4028516791",
    "contentId": "4dcc7ed4-6d15-4170-bad2-fdf28705fbae"
  },
  {
    "name": "Ghost",
    "description": "Fast attack bike fitted with dual rapid-fire plasma cannons. Can boost for extra speed, at the expense of maneuverability.",
    "largeIconImageUrl": "https://content.halocdn.com/media/Default/games/halo-5-guardians/tools-of-destruction/vehicles/ghost-3d8125d531f14b5499eb203bb6689c19.png",
    "smallIconImageUrl": "https://image.halocdn.com:443/?path=https%3a%2f%2fcontent.halocdn.com%2fmedia%2fDefault%2fgames%2fhalo-5-guardians%2ftools-of-destruction%2fvehicles%2fghost-3d8125d531f14b5499eb203bb6689c19.png&width=332&hash=8iIZszbCW4BymoY%2ftsU02sVjy9k1RPVcIR9WPhE%2bNLA%3d",
    "isUsableByPlayer": true,
    "id": "3010146366",
    "contentId": "d760ed2e-8b55-44c0-9b47-fc5c8d44910d"
  },
  {
    "name": "Mongoose",
    "description": "Heavy-duty all-terrain quad bike. A passenger can be accommodated on the rear-facing seat. ",
    "largeIconImageUrl": "https://content.halocdn.com/media/Default/games/halo-5-guardians/tools-of-destruction/vehicles/wargoose-6bfb5d0d8ff34c67ac7537dbecea9f59.png",
    "smallIconImageUrl": "https://image.halocdn.com:443/?path=https%3a%2f%2fcontent.halocdn.com%2fmedia%2fDefault%2fgames%2fhalo-5-guardians%2ftools-of-destruction%2fvehicles%2fwargoose-6bfb5d0d8ff34c67ac7537dbecea9f59.png&width=332&hash=Alksbp7GujgkvJ5tsRpgWqCOoUqpeIvuRAY9Y9dFWRk%3d",
    "isUsableByPlayer": true,
    "id": "1063919886",
    "contentId": "f9b11bd7-7959-4639-94de-a9df329579a5"
  },
  {
    "name": "PHANTOM",
    "description": "Phantom deployable for campaign and warzone",
    "largeIconImageUrl": "https://content.halocdn.com/media/Default/games/halo-5-guardians/default-images/default-vehicle-312x432-217e60cf347c400e9ea0643a931f6dde.png",
    "smallIconImageUrl": "https://image.halocdn.com:443/?path=https%3a%2f%2fcontent.halocdn.com%2fmedia%2fDefault%2fgames%2fhalo-5-guardians%2fdefault-images%2fdefault-vehicle-312x432-217e60cf347c400e9ea0643a931f6dde.png&width=332&hash=bnz5m0PUqdx8urJpI5yTA884lxI9qwM7bQ5lR0Fa8Kc%3d",
    "isUsableByPlayer": false,
    "id": "1977724336",
    "contentId": "54d2716c-b420-4a40-9e93-6636b221177b"
  }
```
