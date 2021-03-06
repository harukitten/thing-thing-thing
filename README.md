<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [About The Event](#about-the-event)
- [Steps for participants:](#steps-for-participants)
- [Class `Creature`](#class-creature)
  - [Properties/Fields](#propertiesfields)
  - [Events](#events)
  - [Ready to Use Methods](#ready-to-use-methods)
- [Tips](#tips)
  - [How to keep your cloned repository up to date](#how-to-keep-your-cloned-repository-up-to-date)
  - [Where to put my files](#where-to-put-my-files)
      - [Where to put my prefabs:](#where-to-put-my-prefabs)
      - [Where to put my materials and scripts](#where-to-put-my-materials-and-scripts)
      - [Where to put my sound files](#where-to-put-my-sound-files)
  - [How to use your own sound files](#how-to-use-your-own-sound-files)
  - [Some Basic about C# Programming](#some-basic-about-c-programming)
  - [Some useful methods from Unity](#some-useful-methods-from-unity)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# About The Event

Saturday, April 14 and Sunday, April 15, 1:00-5:00pm

Asia Art Archive in America

43 Remsen Street, Brooklyn, NY 11201



This event is free and open to the public, but space is limited and registration is required

Please register [here](https://www.eventbrite.com/e/thingthingthing-unity-workshop-and-collective-creation-tickets-44722475127)

An art video game is like daydreaming – a dream that one can go back to over and over again. Objects within the Game are external manifestations of their creators’ spirits. While their creators are tied up with the reality of life, these tiny Objects awaken in this wondrous space of “grandeur” (Gustave Bachelard, 1948), brought to life through the imagination of the Game creators. They twist, turn, wiggle, roll around. On a sunny day, they wander within the Game land, make a friend, sing a song by the river. Gently, they bring together heaven and earth, and open their creators up to the future of reality.

ThingThingThing is an experimental collaboration between Asia Art Archive in America and the artist duo ZZYW, formed by Yang Wang and Zhenzhen Qi. Participants will spend two action-packed days at AAAinA, learning the fundamentals of video game development and making a collective art game along the way. At the end of the two days, the result is a film of the Game that generates its own plot in real time, created by all of the participants using Unity, a video game development platform, and C# as the programming language.

Day One (Saturday, April 14): participants will be supplied with virtual 3D models that roughly invoke humans, animals, or objects. They will learn about creating materials, editing textures, as well as using computer code to manipulate the location, movement, rotation, and size of the models.

Day Two (Sunday, April 15): participants will be supplied with simple computer code, which can be attached to the 3D model and give instructions for how the model should act, such as “make a sound” when it approaches the river or “disperse tiny stars” when meeting a new friend. Participants are also welcome to modify or write their own code to create more involved Game play.

Throughout the entire workshop, the artists will collect the 3D models, or “Things”, made by the participants and place them into a virtual world. At the end of the two-day workshop, we will play the final version of the Game in AAAinA’s screening room and watch our models explore their world and meet each other – thing to thing, while we also get to know one another, human to human.



# Steps for participants:

[Google Doc Link](https://docs.google.com/document/d/18rqBA01xjrEOiLuYqoa7b_HeCmha066y6eLI37iUFIA/edit?usp=sharing)



# Class `Creature`


## Properties/Fields


```csharp
//Environment
float TOD_Data.main.TimeNow; //e.x. 3:30PM will be represented as 15.5
bool TOD_Data.main.IsDay;
bool TOD_Data.main.IsNight; 
bool inWater; //if is in water now
int NeighborCount; //how many neighbors do you have currently
```

## Events

```csharp
void OnSunset();
void OnSunrise();
void OnMeetingSomeone(GameObject other);
void OnLeavingSomeone(GameObject other);
void OnNeighborSpeaking();
void OnNeigborSparkingParticles();
void OnTouchWater();
void OnLeaveWater();
```

## Ready to Use Methods

```csharp

//movement
void SetTarget(Vector3 target);
void StopWalking();
void StopWalking(float forHowManySeconds);
void RestartWalking();
void RandomSetDestination();//get a new random target
void ResetPosition(); //change position to spawn point

//shape and form
void SetScale(Vector3 newScale);
void ChangeColor(Color newColor); //change color, might not work well if you have more than one renderer or more than one material
void ResetColor(); //reset to original color

//social
void Speak(string content, float stayLength);
void Speak(string content);
void Mute(); //Speak no longer works
void DeMute(); //regain ability to Speak again
void Spark(Color particleColor, int numberOfParticles);
void PlaySound(string soundName);
void CreateCube(); //throw a cube on the small ground


```



# Tips

## How to keep your cloned repository up to date

Only do this once

`git remote add upstream https://github.com/ZZYW/thing-thing-thing.git`

Do this to update

`git pull upstream master`

## Where to put my files

#### Where to put my prefabs:
`Resources/Things/[here]`

#### Where to put my materials and scripts
`CREATORS/[your first name]/[here]`

#### Where to put my sound files
`Resources/Sounds/[here]`


## How to use your own sound files

Find a sound file that is one of the formats below

- .Aif.
- .wav.
- .mp3.
- .ogg.

Compress it if necessary, make sure its file size is smaller than 2 MB, and move it into `Resources/Sounds` folder.

Use `PlaySound(“filename”)` to play your sound.


## Some Basic about C# Programming


[If Else Statement](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/if-else)
AND
[For Loop](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/for)

OR

[Everything Else About C#](https://docs.microsoft.com/en-us/dotnet/csharp/index)


## Some useful methods from Unity

```csharp

//Print things to Console for debugging
print(object message);

//Invokes the method methodName in time seconds.
Invoke(string methodName, float time);

//Invokes the method methodName in time seconds, then repeatedly every repeatRate seconds.
InvokeRepeating(string methodName, float time, float repeatRate);

//Cancels all Invoke calls on this MonoBehaviour.
CancelInvoke();


```





