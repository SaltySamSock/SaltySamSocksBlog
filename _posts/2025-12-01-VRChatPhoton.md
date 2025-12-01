---
layout: post
title:  "VRChat Photon"
tag: "Programming, Hacking, VRChat"
---
| EventCode | EventName                     | PayloadType                                                |
|-----------|-------------------------------|------------------------------------------------------------|
| 0         | Unused                        |                                                            |
| 1         | Uspeak                        |                                                            |
| 2         | ExecutiveMessage              |                                                            |
| 3         | SendPastEvents                |                                                            |
| 4         | SyncEvents                    | Dictionary<byte, Il2CppSystem.Object>                      |
| 5         | InitialSyncFinished           | Dictionary<byte, Il2CppSystem.Object>                      |
| 6         | ProcessEvent                  |                                                            |
| 7         | Serialization8                |                                                            |
| 8         | ReceiveInterval               |                                                            |
| 9         | Serialization32               |                                                            |
| 10        | UdonSerialization8            |                                                            |
| 11        | UdonSerialization32           |                                                            |
| 12        | PlayerSerialization8          |                                                            |
| 13        | PlayerSerialization32         |                                                            |
| 14        | PropSerialization8            |                                                            |
| 15        | PropSerialization32           |                                                            |
| 16        | PhysicsSerialization          |                                                            |
| 17        | UdonUnreliableSerialization   |                                                            |
| 18        | UdonNetworkCall               |                                                            |
| 20        | OwnershipCollection           |                                                            |
| 21        | OwnershipRequest              |                                                            |
| 22        | OwnershipTransfer             |                                                            |
| 23        | RestrictedViews               |                                                            |
| 24        | SerializationRecovery         |                                                            |
| 25        | InstanceMetadata              |                                                            |
| 26        | NotifySuspend                 |                                                            |
| 27        | MasterTransfer                | Dictionary<byte, Il2CppSystem.Object>                      |
| 28        | OnPlayerRestored              |                                                            |
| 29        | OnInstanceRestored            |                                                            |
| 30        | RequestNoPersist              | 0                                                          |
| 33        | ExecutiveAction               | Dictionary<byte, Il2CppSystem.Object>                      |
| 34        | SetNetworkLimits              |                                                            |
| 35        | ResetEventCounts              |                                                            |
| 40        | UserModelUpdate               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 41        |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 42        | PlayerProperties              |                                                            |
| 43        | TextChatMessage               | string                                                     |
| 44        | TextChatAction                | byte                                                       |
| 50        | StoreMadePurchase             | null | Dictionary<byte, Il2CppSystem.Object>               |
| 51        | StorePurchaseResult           | int[]                                                      |
| 52        | StoreUsePurchase              | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 53        | StoreListProductOwners        | string[]                                                   |
| 60        | AvatarInteractionList         | int[] | hashtable                                          |
| 64        |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 66        | EAC                           |                                                            |
| 67        | AppD                          |                                                            |
| 69        |                               | byte                                                       |
| 72        | FocusViewEvent                | byte                                                       |
| 73        | AvatarToken                   | Dictionary<byte, Il2CppSystem.Object>                      |
| 74        | PlaceableEvent                | Dictionary<byte, Il2CppSystem.Object>                      |
| 75        | InstanceContentSettingsUpdate | Dictionary<byte, Il2CppSystem.Object>                      |
| 76        | EmojiEvent                    |                                                            |
| 79        |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 86        |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 89        |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 93        |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 99        |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 100       |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 106       |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 121       |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 129       |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 148       |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 156       |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 161       |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 163       |                               |                                                            |
| 169       |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 187       |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 192       |                               | string                                                     |
| 193       |                               |                                                            |
| 196       |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 198       | SerializationRecoveryUnpacked |                                                            |
| 199       | BulkData                      |                                                            |
| 202       |                               | byte                                                       |
| 204       |                               | string                                                     |
| 214       |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 223       |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 224       |                               | byte                                                       |
| 229       |                               | Dictionary<byte, Il2CppSystem.Object>                      |
| 233       |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |
| 242       |                               | string                                                     |
| 253       |                               | VRC.Core.Networking.VRCPhotonEvent.UserModelUpdateProperty |

to be continued
