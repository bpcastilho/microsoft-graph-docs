---
title: "channel resource type"
description: "A channel is a collection of chatMessages within a team. "
author: "nkramer"
localization_priority: Priority
ms.prod: "microsoft-teams"
---

# channel resource type

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

A channel is a collection of [chatMessages](chatmessage.md) within a [team](../resources/team.md). 
A channel represents a topic, and therefore a logical isolation of discussion, within a team. 
Examples can be "Friday Team Lunch" channel, and "Architecture Discussion" channel.


## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[List channels](../api/channel-list.md) | [channel](channel.md) collection | Get the list of channels in this team.|
|[Create channel](../api/channel-post.md) | [channel](channel.md) | Create a new channel by including the display name and description.|
|[Get channel](../api/channel-get.md) | [channel](channel.md) | Read properties and relationships of the channel.|
|[Update channel](../api/channel-patch.md) | [channel](channel.md) | Update properties of the channel.|
|[Delete channel](../api/channel-delete.md) | None | Delete a channel.|
|[List channel messages](../api/channel-list-messages.md)  | [chatMessage](../resources/chatmessage.md) | Get messages in a channel |
|[Send channel message](../api/channel-post-chatmessage.md)  | [chatMessage](../resources/chatmessage.md) | [Send a message to a channel](../api/channel-post-chatmessage.md) |


## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|description|String|Optional textual description for the channel.|
|displayName|String|Channel name as it will appear to the user in Microsoft Teams.|
|id|String|The channels's unique identifier. Read-only.|
|isFavoriteByDefault|Boolean|Whether the channel should automatically be marked 'favorite' for all members of the team. Default: `false`.|
|email|Boolean| The email address for sending messages to the channel. Read-only.|
|webUrl|String|A hyperlink that will navigate to the channel in Microsoft Teams. This is the URL that you get when you right-click a channel in Microsoft Teams and select Get link to channel. This URL should be treated as an opaque blob, and not parsed. Read-only.|


## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|messages|[chatMessage](chatmessage.md) collection|A collection of all the messages in the channel. A navigation property. Nullable. Currently this API only supports reading but will eventually support writing messages too.|
|tabs|[teamsTab](../resources/teamstab.md) collection|A collection of all the tabs in the channel. A navigation property.|


## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "messages"
  ],
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.channel"
}-->

```json
{
  "description": "string",
  "displayName": "string",
  "id": "string (identifier)",
}

```


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "channel resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
    "Error: /api-reference/beta/resources/channel.md:\r\n      Exception processing links.\r\n    System.ArgumentException: Link Definition was null. Link text: !INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)\r\n      at ApiDoctor.Validation.DocFile.get_LinkDestinations()\r\n      at ApiDoctor.Validation.DocSet.ValidateLinks(Boolean includeWarnings, String[] relativePathForFiles, IssueLogger issues, Boolean requireFilenameCaseMatch, Boolean printOrphanedFiles)"
  ]
}
-->
