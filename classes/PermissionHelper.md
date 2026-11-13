[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / PermissionHelper

# Class: PermissionHelper

Static helper for reading the current board member's permissions and feature-toggle
state

## Example

```ts
import { PermissionHelper } from 'alleoWidgetUtils'

if (PermissionHelper.canEdit) {
    // safe to mutate shared state
}

if (PermissionHelper.isPermissionEnough(BoardMemberPermission.Owner)) {
    // current user is an Owner
}
```

## Constructors

### Constructor

```ts
new PermissionHelper(): PermissionHelper;
```

#### Returns

`PermissionHelper`

## Accessors

### boardMemberPermission

#### Get Signature

```ts
get static boardMemberPermission(): BoardMemberPermission;
```

The current user's BoardMemberPermission

##### Example

```ts
const permission = PermissionHelper.boardMemberPermission // e.g. BoardMemberPermission.Editor
```

##### Returns

`BoardMemberPermission`

---

### canAuthor

#### Get Signature

```ts
get static canAuthor(): boolean;
```

Whether the current user can author "premium" board apps.

##### Example

```ts
if (PermissionHelper.canAuthor) {
    showAdvancedSettings()
}
```

##### Returns

`boolean`

---

### canEdit

#### Get Signature

```ts
get static canEdit(): boolean;
```

Whether the current user is allowed to edit the board.
Falls back to `false` when there is no current user.

##### Example

```ts
if (!PermissionHelper.canEdit) return
```

##### Returns

`boolean`

---

### currentUser

#### Get Signature

```ts
get static currentUser(): IBoardUser;
```

The currently signed-in board member, or `null` when no user is available

##### Example

```ts
const userId = PermissionHelper.currentUser?.id
```

##### Returns

`IBoardUser`

## Methods

### featureEnabled()

```ts
static featureEnabled(featureToggle:
  | "InstructureCanvasFiles"
  | "HapticLogin"
  | "ZoomApp"
  | "SlackApp"
  | "MicrosoftCalendar"
  | "SupportChat"
  | "GuidedTours"
  | "LanguageSelect"
  | "ForgotPassword"
  | "InstructureCanvasLogin"
  | "SlackLogin"
  | "ZoomLogin"
  | "GoogleLogin"
  | "MicrosoftLogin"
  | "WebexLogin"
  | "InstructureCanvasRegister"
  | "SlackRegister"
  | "ZoomRegister"
  | "GoogleRegister"
  | "MicrosoftRegister"
  | "HapticRegister"
  | "WebexRegister"
  | "SlackConnect"
  | "ZoomConnect"
  | "GoogleConnect"
  | "MicrosoftConnect"
  | "GoogleFiles"
  | "MicrosoftFiles"
  | "BoxFiles"
  | "MicrosoftMeetings"
  | "GoogleMeetings"
  | "ZoomMeetings"
  | "LifesizeMeetings"
  | "WebexMeetings"
  | "BlueJeansMeetings"
  | "ChimeMeetings"
  | "AlleoMeetings"
  | "WebinarHapticMeeting"
  | "CallRecording"
  | "CallRecordingTranscript"
  | "SuspendVoiceForHiddenCallVideoStreams"
  | "SuspendVoiceForUsersInSharedAreas"
  | "VonageWebRtc"
  | "LiveKitWebRtc"
  | "P2PWebRtcTurn"
  | "UserInviteLinks"
  | "UserNotifications"
  | "ThirdPartyNotifications"
  | "BypassGuestJoinBoardPage"
  | "ChangeEmail"
  | "RequireUserEmailConfirmation"
  | "RequireInviteForRegistration"
  | "CommunityPortal"
  | "AdminInUseDisplayNavigation"
  | "ThirdPartyConnectionProxy"
  | "AllowMultiDeviceUserSessions"
  | "AnalyticsSessionsExplorer"
  | "CoverImageSearch"
  | "Calendar"
  | "BoardTemplateSelector"
  | "CreateBoard"
  | "FeaturedBoardTemplates"
  | "BoardArchive"
  | "PublicBoardsHistory"
  | "MapBoardType"
  | "InfiniteBoardType"
  | "FixedBoardType"
  | "WebpageBoardType"
  | "MainToolbar"
  | "DrawingMenu"
  | "ToolsMenu"
  | "MoreToolsMenu"
  | "ColorMenu"
  | "ExperimentalMenu"
  | "WidgetBrowserMenu"
  | "BoardAreas"
  | "BoardTopBar"
  | "PresentationTools"
  | "MeetingSessions"
  | "UserPanel"
  | "ActivityPanel"
  | "LayersPanel"
  | "ManageGuests"
  | "AssetPanel"
  | "AssetDownload"
  | "AssetFolderDownload"
  | "AssetUpload"
  | "AssetUploadThirdPartyProvider"
  | "AssetMetaEdit"
  | "AssetReplace"
  | "AssetAppStreamEdit"
  | "OfficeDocumentUpload"
  | "FileContainerScopeUser"
  | "ViewsPanel"
  | "ObjectActions"
  | "ObjectActionFlows"
  | "CursorMode"
  | "MarkerMode"
  | "MarkerDrawingMode"
  | "EraserMode"
  | "OverviewMode"
  | "BoardSettingsDialog"
  | "BoardHotkeys"
  | "TextObject"
  | "StickyNoteObject"
  | "ScreenShareObject"
  | "ScreenShareControl"
  | "AnonymousScreenShare"
  | "LiveVideoObject"
  | "LiveVideoControl"
  | "LiveVideoActiveSpeaker"
  | "LiveVideoRemoteRoomStart"
  | "StickerObject"
  | "StickyPadObject"
  | "VncObject"
  | "AppStreamFirefoxObject"
  | "RemoteAppWidgetObject"
  | "RichTextObject"
  | "EmbedObject"
  | "ContainerObject"
  | "SlideObject"
  | "ModelObject"
  | "CommentObject"
  | "ClockObject"
  | "AdaptiveCardObject"
  | "BoardCalendarObject"
  | "ExternalWidgetObject"
  | "CollaborativeNotepadObject"
  | "SpreadsheetWidgetObject"
  | "Spotlight"
  | "UserCursorTimeout"
  | "UserMouseTrails"
  | "UserUnmuteVoicePrompt"
  | "GlobalSearch"
  | "HapticSearch"
  | "HapticSearchAllBoards"
  | "HapticSearchAllFiles"
  | "SearchExternalProviders"
  | "AdaptiveCardDesigner"
  | "Chat"
  | "ChatMentions"
  | "VoiceChat"
  | "VoiceChatJoinCall"
  | "PdfExport"
  | "ServerSidePdfExport"
  | "RequireTwoFactorEmailAuthentication"
  | "P2PVideoPlaybackSync"
  | "ObjectDrawArea"
  | "ExperimentalBoardPreview"
  | "LongpressToSelectObjectsSetting"
  | "ObjectConnections"
  | "DesignMode"
  | "AnonymousSignInOrUp"
  | "ContributorPermission"
  | "ClearBoard"
  | "ExitBoard"
  | "BoardQrCode"
  | "SupportDialog"
  | "SupportUploadBoardLog"
  | "RecordDialog"
  | "SlideAddContextMenu"
  | "SlidePresentContextMenu"
  | "SlideSettingsContextMenu"
  | "FollowSlideTemplateChanges"
  | "DocumentCloudEditContextMenu"
  | "DocumentCloudUpdateContextMenu"
  | "TextColorsContextMenu"
  | "TextFontsSubMenu"
  | "StickyNoteFontsContextMenu"
  | "StickyNoteBackgroundColorContextMenu"
  | "StickyNoteOutlineColorContextMenu"
  | "StickyNoteShapeContextMenu"
  | "PathStrokeColorContextMenu"
  | "MoreContextMenu"
  | "CommentsContextMenu"
  | "PerLocationAutoAdvanceTimeout"
  | "BoardPresentationAutoStart"
  | "ContextMenuAssetDownload"
  | "ObjectActionOnDownloadFile"
  | "StartPendoGuideObjectAction"
  | "ProxyCallUrlObjectAction"
  | "ProxyPayloadToRoomObjectAction"
  | "RoomActions"
  | "ContainerObjectActions"
  | "ObjectReactions"
  | "MeetingSatisfactionSurvey"
  | "MeetingEndEmailNotification"
  | "ShareBoardToRoom"
  | "ShareBoard"
  | "ShareBoardWithRoom"
  | "ShareBoardWithRoomQrCode"
  | "InteractiveAgentRemoteShareControl"
  | "InteractiveAgentPointerEventApi"
  | "PublicLinkSharing"
  | "PublicLinkViewer"
  | "PublicLinkEditor"
  | "PublicLinkContributor"
  | "PublicLinkIsolatedViewer"
  | "PublicLinkIsolatedEditor"
  | "RoomCursorMode"
  | "RoomMarkerMode"
  | "RoomColorMenu"
  | "RoomMarkerDrawingMode"
  | "RoomEraserMode"
  | "RoomCanvasSettings"
  | "RoomSave"
  | "RoomCanvasColor"
  | "RoomCanvasGrid"
  | "RoomNavigationLongpressPanel"
  | "RoomConnectObject"
  | "RoomOpenObject"
  | "RoomThirdPartyMeeting"
  | "ReadOnlyVoice"
  | "ReadOnlyExit"
  | "HighLatencyNotification"
  | "AVISPLAMXIntegration"
  | "BoardAppsAuthoring"
  | FeatureToggle): boolean;
```

Checks whether a given feature toggle is enabled on the current board.

#### Parameters

| Parameter       | Type                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Description                                       |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| `featureToggle` | \| `"InstructureCanvasFiles"` \| `"HapticLogin"` \| `"ZoomApp"` \| `"SlackApp"` \| `"MicrosoftCalendar"` \| `"SupportChat"` \| `"GuidedTours"` \| `"LanguageSelect"` \| `"ForgotPassword"` \| `"InstructureCanvasLogin"` \| `"SlackLogin"` \| `"ZoomLogin"` \| `"GoogleLogin"` \| `"MicrosoftLogin"` \| `"WebexLogin"` \| `"InstructureCanvasRegister"` \| `"SlackRegister"` \| `"ZoomRegister"` \| `"GoogleRegister"` \| `"MicrosoftRegister"` \| `"HapticRegister"` \| `"WebexRegister"` \| `"SlackConnect"` \| `"ZoomConnect"` \| `"GoogleConnect"` \| `"MicrosoftConnect"` \| `"GoogleFiles"` \| `"MicrosoftFiles"` \| `"BoxFiles"` \| `"MicrosoftMeetings"` \| `"GoogleMeetings"` \| `"ZoomMeetings"` \| `"LifesizeMeetings"` \| `"WebexMeetings"` \| `"BlueJeansMeetings"` \| `"ChimeMeetings"` \| `"AlleoMeetings"` \| `"WebinarHapticMeeting"` \| `"CallRecording"` \| `"CallRecordingTranscript"` \| `"SuspendVoiceForHiddenCallVideoStreams"` \| `"SuspendVoiceForUsersInSharedAreas"` \| `"VonageWebRtc"` \| `"LiveKitWebRtc"` \| `"P2PWebRtcTurn"` \| `"UserInviteLinks"` \| `"UserNotifications"` \| `"ThirdPartyNotifications"` \| `"BypassGuestJoinBoardPage"` \| `"ChangeEmail"` \| `"RequireUserEmailConfirmation"` \| `"RequireInviteForRegistration"` \| `"CommunityPortal"` \| `"AdminInUseDisplayNavigation"` \| `"ThirdPartyConnectionProxy"` \| `"AllowMultiDeviceUserSessions"` \| `"AnalyticsSessionsExplorer"` \| `"CoverImageSearch"` \| `"Calendar"` \| `"BoardTemplateSelector"` \| `"CreateBoard"` \| `"FeaturedBoardTemplates"` \| `"BoardArchive"` \| `"PublicBoardsHistory"` \| `"MapBoardType"` \| `"InfiniteBoardType"` \| `"FixedBoardType"` \| `"WebpageBoardType"` \| `"MainToolbar"` \| `"DrawingMenu"` \| `"ToolsMenu"` \| `"MoreToolsMenu"` \| `"ColorMenu"` \| `"ExperimentalMenu"` \| `"WidgetBrowserMenu"` \| `"BoardAreas"` \| `"BoardTopBar"` \| `"PresentationTools"` \| `"MeetingSessions"` \| `"UserPanel"` \| `"ActivityPanel"` \| `"LayersPanel"` \| `"ManageGuests"` \| `"AssetPanel"` \| `"AssetDownload"` \| `"AssetFolderDownload"` \| `"AssetUpload"` \| `"AssetUploadThirdPartyProvider"` \| `"AssetMetaEdit"` \| `"AssetReplace"` \| `"AssetAppStreamEdit"` \| `"OfficeDocumentUpload"` \| `"FileContainerScopeUser"` \| `"ViewsPanel"` \| `"ObjectActions"` \| `"ObjectActionFlows"` \| `"CursorMode"` \| `"MarkerMode"` \| `"MarkerDrawingMode"` \| `"EraserMode"` \| `"OverviewMode"` \| `"BoardSettingsDialog"` \| `"BoardHotkeys"` \| `"TextObject"` \| `"StickyNoteObject"` \| `"ScreenShareObject"` \| `"ScreenShareControl"` \| `"AnonymousScreenShare"` \| `"LiveVideoObject"` \| `"LiveVideoControl"` \| `"LiveVideoActiveSpeaker"` \| `"LiveVideoRemoteRoomStart"` \| `"StickerObject"` \| `"StickyPadObject"` \| `"VncObject"` \| `"AppStreamFirefoxObject"` \| `"RemoteAppWidgetObject"` \| `"RichTextObject"` \| `"EmbedObject"` \| `"ContainerObject"` \| `"SlideObject"` \| `"ModelObject"` \| `"CommentObject"` \| `"ClockObject"` \| `"AdaptiveCardObject"` \| `"BoardCalendarObject"` \| `"ExternalWidgetObject"` \| `"CollaborativeNotepadObject"` \| `"SpreadsheetWidgetObject"` \| `"Spotlight"` \| `"UserCursorTimeout"` \| `"UserMouseTrails"` \| `"UserUnmuteVoicePrompt"` \| `"GlobalSearch"` \| `"HapticSearch"` \| `"HapticSearchAllBoards"` \| `"HapticSearchAllFiles"` \| `"SearchExternalProviders"` \| `"AdaptiveCardDesigner"` \| `"Chat"` \| `"ChatMentions"` \| `"VoiceChat"` \| `"VoiceChatJoinCall"` \| `"PdfExport"` \| `"ServerSidePdfExport"` \| `"RequireTwoFactorEmailAuthentication"` \| `"P2PVideoPlaybackSync"` \| `"ObjectDrawArea"` \| `"ExperimentalBoardPreview"` \| `"LongpressToSelectObjectsSetting"` \| `"ObjectConnections"` \| `"DesignMode"` \| `"AnonymousSignInOrUp"` \| `"ContributorPermission"` \| `"ClearBoard"` \| `"ExitBoard"` \| `"BoardQrCode"` \| `"SupportDialog"` \| `"SupportUploadBoardLog"` \| `"RecordDialog"` \| `"SlideAddContextMenu"` \| `"SlidePresentContextMenu"` \| `"SlideSettingsContextMenu"` \| `"FollowSlideTemplateChanges"` \| `"DocumentCloudEditContextMenu"` \| `"DocumentCloudUpdateContextMenu"` \| `"TextColorsContextMenu"` \| `"TextFontsSubMenu"` \| `"StickyNoteFontsContextMenu"` \| `"StickyNoteBackgroundColorContextMenu"` \| `"StickyNoteOutlineColorContextMenu"` \| `"StickyNoteShapeContextMenu"` \| `"PathStrokeColorContextMenu"` \| `"MoreContextMenu"` \| `"CommentsContextMenu"` \| `"PerLocationAutoAdvanceTimeout"` \| `"BoardPresentationAutoStart"` \| `"ContextMenuAssetDownload"` \| `"ObjectActionOnDownloadFile"` \| `"StartPendoGuideObjectAction"` \| `"ProxyCallUrlObjectAction"` \| `"ProxyPayloadToRoomObjectAction"` \| `"RoomActions"` \| `"ContainerObjectActions"` \| `"ObjectReactions"` \| `"MeetingSatisfactionSurvey"` \| `"MeetingEndEmailNotification"` \| `"ShareBoardToRoom"` \| `"ShareBoard"` \| `"ShareBoardWithRoom"` \| `"ShareBoardWithRoomQrCode"` \| `"InteractiveAgentRemoteShareControl"` \| `"InteractiveAgentPointerEventApi"` \| `"PublicLinkSharing"` \| `"PublicLinkViewer"` \| `"PublicLinkEditor"` \| `"PublicLinkContributor"` \| `"PublicLinkIsolatedViewer"` \| `"PublicLinkIsolatedEditor"` \| `"RoomCursorMode"` \| `"RoomMarkerMode"` \| `"RoomColorMenu"` \| `"RoomMarkerDrawingMode"` \| `"RoomEraserMode"` \| `"RoomCanvasSettings"` \| `"RoomSave"` \| `"RoomCanvasColor"` \| `"RoomCanvasGrid"` \| `"RoomNavigationLongpressPanel"` \| `"RoomConnectObject"` \| `"RoomOpenObject"` \| `"RoomThirdPartyMeeting"` \| `"ReadOnlyVoice"` \| `"ReadOnlyExit"` \| `"HighLatencyNotification"` \| `"AVISPLAMXIntegration"` \| `"BoardAppsAuthoring"` \| `FeatureToggle` | The FeatureToggle (or its string value) to check. |

#### Returns

`boolean`

`true` if the feature is enabled on `haptic.board`, otherwise `false`.

#### Example

```ts
if (PermissionHelper.featureEnabled(FeatureToggle.GuidedTours)) {
    startGuidedTour()
}
```

---

### isMyPermissionEnoughFor()

```ts
static isMyPermissionEnoughFor(feature:
  | "add-object"
  | "add-widget"
  | "add-slide"
  | "add-sticky-note"
  | "open-settings"
  | "move-object-to-container"
  | "remove-object-from-container"
  | "edit-object"
  | "edit-object-content"
  | "edit-object-tags"
  | "open-widget-organization-docs"
  | "delete-object"
  | "trigger-action-effect"
  | "can-use-ai"
  | "can-use-ai-board-edit"
  | "can-use-ai-transcribe-audio"
  | "can-use-ai-generate-image", object?: IBoardObject | IBoardObject[]): boolean;
```

Checks whether the current user has enough permission to perform a given action.

Supported features and the minimum permission each one requires:

- `add-object`: Editor
- `add-widget`: Editor
- `add-slide`: Editor
- `add-sticky-note`: Contributor
- `open-settings`: Editor
- `move-object-to-container`: Contributor. Also covers moving an object from one container to another.
- `remove-object-from-container`: Contributor. Only for taking an object out of all containers (onto the bare board);
  moving it into a different container is `move-object-to-container`, not a removal.
- `edit-object`: Editor
- `edit-object-content`: Contributor when all objects are notepads, sticky notes or widgets; otherwise Editor (including when no objects are given)
- `edit-object-tags`: Editor
- `delete-object`: Editor
- `open-widget-organization-docs`: Owner
- `trigger-action-effect`: everyone
- `can-use-ai`: everyone
- `can-use-ai-board-edit`: Editor
- `can-use-ai-transcribe-audio`: everyone
- `can-use-ai-generate-image`: everyone

#### Parameters

| Parameter | Type                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Default value | Description                                                         |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ------------------------------------------------------------------- |
| `feature` | \| `"add-object"` \| `"add-widget"` \| `"add-slide"` \| `"add-sticky-note"` \| `"open-settings"` \| `"move-object-to-container"` \| `"remove-object-from-container"` \| `"edit-object"` \| `"edit-object-content"` \| `"edit-object-tags"` \| `"open-widget-organization-docs"` \| `"delete-object"` \| `"trigger-action-effect"` \| `"can-use-ai"` \| `"can-use-ai-board-edit"` \| `"can-use-ai-transcribe-audio"` \| `"can-use-ai-generate-image"` | `undefined`   | The action to check permission for.                                 |
| `object?` | `IBoardObject` \| `IBoardObject`[]                                                                                                                                                                                                                                                                                                                                                                                                                   | `[]`          | The object(s) to check against. Only used by `edit-object-content`. |

#### Returns

`boolean`

`true` if the current user has sufficient permission, otherwise `false`.

#### Example

```ts
if (PermissionHelper.isMyPermissionEnoughFor('add-object')) {
    // safe to add an object
}
```

---

### isPermissionEnough()

```ts
static isPermissionEnough(requiredPermission?: BoardMemberPermission, permission?: BoardMemberPermission): boolean;
```

Compares a permission against a required permission level using the
`Viewer` < `Contributor` < `Editor` < `Owner` hierarchy.

#### Parameters

| Parameter             | Type                    | Default value                            | Description                                                                                            |
| --------------------- | ----------------------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| `requiredPermission?` | `BoardMemberPermission` | `BoardMemberPermission.Owner`            | The minimum BoardMemberPermission needed. Defaults to `Owner`.                                         |
| `permission?`         | `BoardMemberPermission` | `PermissionHelper.boardMemberPermission` | The permission to check. Defaults to [PermissionHelper.boardMemberPermission](#boardmemberpermission). |

#### Returns

`boolean`

`true` if `permission` meets or exceeds `requiredPermission`.

#### Example

```ts
// Uses the current user's permission implicitly
PermissionHelper.isPermissionEnough(BoardMemberPermission.Contributor)

// Explicit comparison
PermissionHelper.isPermissionEnough(BoardMemberPermission.Editor, BoardMemberPermission.Owner) // true
```

---

### showPermissionError()

```ts
static showPermissionError(message?: string): void;
```

Logs a permission error and shows a warning notification to the user.

#### Parameters

| Parameter  | Type     | Default value                              | Description                                                           |
| ---------- | -------- | ------------------------------------------ | --------------------------------------------------------------------- |
| `message?` | `string` | `'You do not have permission to do this!'` | The text shown to the user. Defaults to a generic permission message. |

#### Returns

`void`
