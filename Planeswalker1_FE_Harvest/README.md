#Planeswalker1 Version 0.1
#(Forked from UOMP1 version 1.7.4)

This is the first Planeswalker package forked from the Unwritten Legends Official Mudlet package. This package activates interface upon login and harvests all FE tags to a table variable called interfaceTable as well as throws events for every FE Capture to be used in modular additions to this basic package.

#Namespace:
This package uses the Planeswalker namespace, replacing the original UOMP namespace. The Planeswalker1 FE Capture folder initializes this namespace.

#Interface Table:

The following variables may be accessed through ```Planeswalker.interfaceTable["variable"]``` with the quotes included. It is advised that the variables be used in scripts and functions by first assigning them to a local variable first.

Interface Tag       | Description
-------------       | -----------
arcana              | The character's aracan captured from the FE
age                 | The character's age captured from the FE
bleeding limbs      | The number of bleeding limbs calculated from the limb tags from the FE
deity               | The character's deity captured from the FE
dominant hand       | The character's dominant hand captured from the FE
essence             | The character's essence captured from the FE
estimated bleeding  | The estimated bleed rate calculated from the limb tags from the FE. This will tend to overestimate
experience          | The character's experience captured from the FE
experience to level | The character's experience to level captured from the FE
fame                | The character's fame captured from the FE
first name          | The character's first name captured from the FE
gender              | The character's gender captured from the FE
ht                  | The character's healingtime captured from the FE
language            | The character's current language captured from the FE
languages           | The character's known languages captured from the FE
last name           | The character's last name captured from the FE
left hand           | The item in the character's left hand captured from the FE
lessons             | The character's lessons captured from the FE
level               | The character's level captured from the FE
lifetime fame       | The character's lifetime fame captured from the FE
maimed limbs        | The number of maimed limbs calculated from the limb tags from the FE
martial art         | The character's current martial art captured from the FE
martial arts        | The character's known martial arts captured from the FE
maximum essence     | The character's maximum essence captured from the FE
maximum ht          | The maximum healingtime incurred recently, derived from ht.
maximum lessons     | The character's maximum lessons per day captured from the FE
maximum pt          | The maximum preptime incurred recently, derived from pt.
maximum rt          | The maximum roundtime incurred recently, derived from rt.
maximum st          | The maximum stun time incurred recently, derived from st.
maximum stamina     | The character's maximum stamina captured from the FE
maximum ut          | The maximum unconscious time incurred recently, derived from ut.
maximum vitality    | The character's maximum vitality captured from the FE
mutilated limbs     | The number of mutilated limbs calculated from the limb tags from the FE
patron moon         | The character's patron moon captured from the FE
position            | The character's position captured from the FE
posttitle           | The character's current posttitle captured from the FE
pretitle            | The character's current pretitle captured from the FE
profession          | The character's profession captured from the FE
pt                  | The character's preptime captured from the FE
race                | The character's race captured from the FE
right hand          | The item in the character's right hand captured from the FE
room                | The character's current room captured from the FE
rt                  | The character's roundtime captured from the FE
skill points        | The character's skill points captured from the FE
st                  | The character's stun time captured from the FE
stamina             | The character's stamina captured from the FE
stance              | The character's stance captured from the FE
subrace             | The character's subrace captured from the FE
true name           | The character's true first name, unmodified by effects, captured from the FE
ut                  | The character's unconscious time captured from the FE
vitality            | The character's vitality captured from the FE
willpower           | The character's willpower captured from the FE
wounded limbs       | The number of wounded limbs calculated from the limb tags from the FE

The following variables may be accessed through ```Planeswalker.interfaceTable.Limbs["limb name"]```

Key       | Description
---       | -----------
bleedrate | The current descriptive bleed rate of the limb: nothing, slightly, lightly, moderately, seriously, profusely
status    | The status of the limb: healthy, maimed, mutilated
wounds    | The number of wounds on the limb

#Events:

The following events are thrown when FE tags are sent by Unwritten Legends to Mudlet. You may use these events in your own scripts without adding triggers.

Event                    | Description | Sample Code
-----                    | ----------- | -----------
arcanaCapture            | Raised whenever the character's arcana is captured from the FE tags.                                                                                                                                         | raiseEvent("arcanaCapture", arcana)
ageCapture               | Raised whenever the character's age is captured from the FE tags.                                                                                                                                            | raiseEvent("ageCapture", age)
bleedingLimbsCapture     | Raised whenever the number of bleeding limbs is calculated from the limb FE tags.                                                                                                                            | raiseEvent("bleedingLimbsCapture", numberOfBleedingLimbs)
deityCapture             | Raised whenever the character's deity is captured from the FE tags.                                                                                                                                          | raiseEvent("deityCapture", deity)
dominantHandCapture      | Raised whenever the character's dominant hand is captured from the FE tags.                                                                                                                                  | raiseEvent("dominantHandCapture", dominantHand)
essenceCapture           | Raised whenever the character's essence and maximum essence are captured from the FE tags.                                                                                                                   | raiseEvent("essenceCapture", essence, maximumEssence)
estimatedBleedingCapture | Raised whenever the bleed rate is calculated from the limb FE tags.                                                                                                                                          | raiseEvent("estimatedBleedingCapture", estimatedBleedingRate)
exitCapture              | Raised whenever an exit is captured from the FE tags.                                                                                                                                                        |
experienceCapture        | Raised whenever the character's experience is captured from the FE tags. This appends "n" to the front of the value to bypass a mudlet bug. To get rid of the "n", use string.gsub(argument,"n","")          | raiseEvent("experienceCapture", "n"..experience)
experienceToLevelCapture | Raised whenever the character's experience to level is captured from the FE tags. This appends "n" to the front of the value to bypass a mudlet bug. To get rid of the "n", use string.gsub(argument,"n","") | raiseEvent("experienceToLevelCapture", "n"..experienceToLevel)
fameCapture              | Raised whenever the character's fame and lifetime fame are captured from the FE tags.                                                                                                                        | raiseEvent("fameCapture", fame, lifetimeFame)
genderCapture            | Raised whenever the character's gender is captured from the FE tags.                                                                                                                                         | raiseEvent("genderCapture", gender)
htCapture                | Raised whenever the character's healing time is captured from the FE tags.                                                                                                                                   | raiseEvent("htCapture", healingTime)                                       |
htCaptureDouble          | Raised whenever the character's healing time is captured from the FE tags.                                                                                                                                   | raiseEvent("htCapture", healingTime, maximumHealingTime)
languageCapture          | Raised whenever the character's current language is captured from the FE tags.                                                                                                                               | raiseEvent("languageCapture", language)
languagesCapture         | Raised whenever the character's known languages are captured from the FE tags.                                                                                                                               | raiseEvent("languagesCapture", languages)
leftHandCapture          | Raised whenever the item in the character's left hand is captured from the FE tags.                                                                                                                          | raiseEvent("leftHandCapture", leftHandItem)
lessonsCapture           | Raised whenever the character's lessons and maximum lessons are captured from the FE tags.                                                                                                                   | raiseEvent("lessonsCapture", lessons, maximumLessons)
levelCapture             | Raised whenever the character's level is captured from the FE tags.                                                                                                                                          | raiseEvent("levelCapture", level)
limbCapture              | Raised whenever data about the character's limbs is captured from the FE tags.                                                                                                                               | raiseEvent("limbCapture", limbName, limbStatus, numberOfWounds, bleedRate)
loggedIn                 | Raised when you log in to Unwritten Legends.                                                                                                                                                                 | raiseEvent("loggedIn")
maimedLimbsCapture       | Raised whenever the number of maimed limbs is calculated from the limb FE tags.                                                                                                                              | raiseEvent("maimedLimbsCapture", numberOfMaimedLimbs)
martialArtCapture        | Raised whenever the character's current martial art is captured from the FE tags.                                                                                                                            | raiseEvent("martialArtCapture", languages)
martialArtsCapture       | Raised whenever the character's known martial arts are captured from the FE tags.                                                                                                                            | raiseEvent("martialArtsCapture", languages)
mutilatedLimbsCapture    | Raised whenever the number of mutilated limbs is calculated from the limb FE tags.                                                                                                                           | raiseEvent("mutilatedLimbsCapture", numberOfMutilatedLimbs)
nameCapture              | Raised whenever the character's name is captured from the FE tags.                                                                                                                                           | raiseEvent("nameCapture", firstName, lastName)
patronMoonCapture        | Raised whenever the character's patron moon is captured from the FE tags.                                                                                                                                    | raiseEvent("patronMoonCapture", patronMoon)
positionCapture          | Raised whenever the character's position is captured from the FE tags.                                                                                                                                       | raiseEvent("positionCapture", position)
postTitleCapture         | Raised whenever the character's posttitle is captured from the FE tags.                                                                                                                                      | raiseEvent("postTitleCapture", postTitle)
preTitleCapture          | Raised whenever the character's pretitle is captured from the FE tags.                                                                                                                                       | raiseEvent("preTitleCapture", preTitle)
professionCapture        | Raised whenever the character's profession is captured from the FE tags.                                                                                                                                     | raiseEvent("professionCapture", profession)
ptCapture                | Raised whenever the character's prep time is captured from the FE tags.                                                                                                                                      | raiseEvent("ptCapture", prepTime)
ptCaptureDouble          | Raised whenever the character's prep time is captured from the FE tags.                                                                                                                                      | raiseEvent("ptCapture", prepTime, maximumPrepTime)
raceCapture              | Raised whenever the character's race is captured from the FE tags.                                                                                                                                           | raiseEvent("raceCapture", race)
rightHandCapture         | Raised whenever the item in the character's right hand is captured from the FE tags.                                                                                                                         | raiseEvent("rightHandCapture", rightHandItem)
roomCapture              | Raised whenever the character's current room is captured from the FE tags.                                                                                                                                   | raiseEvent("roomCapture", room)
rtCapture                | Raised whenever the character's current roundtime is captured from the FE tags.                                                                                                                              | raiseEvent("rtCapture", roundtime)
rtCaptureDouble          | Raised whenever the character's current roundtime is captured from the FE tags.                                                                                                                              | raiseEvent("rtCapture", roundtime, maximumroundtime)
skillPointsCapture       | Raised whenever the character's skill points is captured from the FE tags.                                                                                                                                   | raiseEvent("skillPointsCapture", skillPoints)
specializationCapture    | Raised whenever the character's specialization is captured from the FE tags.                                                                                                                                 | raiseEvent("specializationCapture", specialization)
spellsCapture            | Raised whenever the character's known spell schools are captured from the FE tags.                                                                                                                           | raiseEvent("spellsCapture", spells)
stCapture                | Raised whenever the character's current stun time is captured from the FE tags.                                                                                                                              | raiseEvent("stCapture", stunTime)
stCaptureDouble          | Raised whenever the character's current stun time is captured from the FE tags.                                                                                                                              | raiseEvent("stCapture", stunTime, maximumStunTime)
staminaCapture           | Raised whenever the character's stamina and maximum stamina are captured from the FE tags.                                                                                                                   | raiseEvent("staminaCapture", stamina, maximumStamina)
stanceCapture            | Raised whenever the character's stance is captured from the FE tags.                                                                                                                                         | raiseEvent("stanceCapture", stance)
subraceCapture           | Raised whenever the character's subrace is captured from the FE tags.                                                                                                                                        | raiseEvent("subraceCapture", subrace)
staminaCapture           | Raised whenever the character's stamina and maximum stamina are captured from the FE tags.                                                                                                                   | raiseEvent("staminaCapture", stamina, maximumStamina)
trueNameCapture          | Raised whenever the character's true name is captured from the FE tags.                                                                                                                                      | raiseEvent("trueNameCapture", truename)
utCapture                | Raised whenever the character's current unconscious time is captured from the FE tags.                                                                                                                       | raiseEvent("utCapture", unconsciousTime)
utCaptureDouble          | Raised whenever the character's current unconscious time is captured from the FE tags.                                                                                                                       | raiseEvent("utCapture", unconsciousTime, maximumUnconsciousTime)
vitalityCapture          | Raised whenever the character's vitality and maximum vitality are captured from the FE tags.                                                                                                                 | raiseEvent("vitalityCapture", vitality, maximumVitality)
willpowerCapture         | Raised whenever the character's willpower and maximum willpower are captured from the FE tags.                                                                                                               | raiseEvent("willpowerCapture", willpower, maximumWillpower)
woundedLimbsCapture      | Raised whenever the number of wounded limbs is calculated from the limb FE tags.                                                                                                                             | raiseEvent("woundedLimbsCapture", numberOfWoundedLimbs)

Scripts and Functions:

pw1DoubleEventHandler(eventName, argumentOne, argumentTwo)  - Handles events with two arguments. Handles the following events:
essenceCapture
fameCapture
lessonsCapture
nameCapture
staminaCapture
vitalityCapture
willpowerCapture

pw1EventHandler(eventName) - Handles events without any arguments. Handles the following events:
loggedIn

pw1QuadEventHandler(eventName, argumentOne, argumentTwo, argumentThree, argumentFour)  - Handles events with four arguments. Handles the following events:
limbCapture

pw1SingleEventHandler(eventName, argument)  - Handles events with one argument. Handles the following events:
ageCapture
arcanaCapture
bleedingLimbsCapture
deityCapture
dominantHandCapture
estimatedBleedingCapture
genderCapture
experienceCapture
experienceToLevelCapture
languageCapture
languagesCapture
leftHandCapture
levelCapture
maimedLimbsCapture
martialArtCapture
martialArtsCapture
mutilatedLimbsCapture
patronMoonCapture
positionCapture
postTitleCapture
preTitleCapture
professionCapture
raceCapture
roomCapture
rtCapture
skillpointsCapture
specializationCapture
spellsCapture
stanceCapture
stCapture
subraceCapture
utCapture
woundedLimbsCapture
