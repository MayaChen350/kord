# 0.15.0

## Additions

* Add `User.isSelf` (by @Taubsie in #950)
* Publish snapshots to https://repo.kord.dev/snapshots (#961)
* Document deprecation cycle of deprecated declarations (#969)
* Add `UserMessageCreateBuilder.enforceNonce` (by @DRSchlaubi in #971)
* Implement Monetization (by @viztea in #932)
* Add `MemberProfileAutoModerationRule` (#974)

## Changes

* Bump `DeprecationLevel`s after 0.14.0 (#944)
* Update Auto Moderation builders (#979)
* Link to JDK 23 in Dokka output (#980)

## Fixes

* Fix deserialization of members (by @NoComment1105 in #955)
* Fix deserialization of `Heartbeat` events (#957)
* Fix `getMemberOrNull` and `getGuildMembers` caching only user data (by @Galarzaa90 in #964)
* Fix misuse of reified type parameters (#981)

## Dependencies

Updated in #942, #954, #958, #975, #976, and #986 (not including dependencies only needed for developing Kord)

* Kotlin 1.9.24 -> 2.0.21
* Ktor 2.3.11 -> 3.0.0
* kotlinx.coroutines 1.8.1 -> 1.9.0
* kotlinx.serialization 1.6.3 -> 1.7.3
* kotlinx-datetime 0.6.0 -> 0.6.1
* kord-cache 0.4.0 -> 0.5.4
* kotlin-logging 6.0.9 -> 7.0.0
* SLF4J 2.0.13 -> 2.0.16
* kotlin-node 20.11.30-pre.751 -> 22.5.4-pre.818
* kotlin-multiplatform-bignum 0.3.9 -> 0.3.10
* Stately 2.0.7 -> 2.1.0
* AtomicFU 0.24.0 -> 0.25.0

# 0.14.0

## Additions

* Support other `SerialFormat`s in `LongOrStringSerializer` (#937)

## Changes

* Bump `DeprecationLevel`s after 0.13.0 (#908)
* Rewrite `Event.DeserializationStrategy` (#923)
* Deprecate application command events (#927)
* Rewrite `VoiceEvent.DeserializationStrategy` (#925)
* Switch to OkHttp as http client on jvm (by @DRSchlaubi in #928)

## Fixes

* `DiscordVoiceState.member` uses incorrect serial name (by @viztea in #914)
* Use actual zero width space in `EmbedBuilder` (by @matytyma in #917)
* Fix some cache links (#934)

## Dependencies

Updated in #920, #929 and #943

* Gradle 8.5 -> 8.7
* Kotlin 1.9.21 -> 1.9.24
* Ktor 2.3.7 -> 2.3.11
* kotlinx.coroutines 1.7.3 -> 1.8.1
* kotlinx.serialization 1.6.2 -> 1.6.3
* kotlinx-datetime 0.5.0 -> 0.6.0
* kotlin-logging 6.0.1 -> 6.0.9
* SLF4J 2.0.9 -> 2.0.13
* kotlin-node 18.16.12-pre.619 -> 20.11.30-pre.751
* kotlin-multiplatform-bignum 0.3.8 -> 0.3.9
* Stately 2.0.6 -> 2.0.7
* KSP 1.9.21-1.0.16 -> 1.9.24-1.0.20
* KotlinPoet 1.15.3 -> 1.16.0
* JUnit Jupiter 5.10.1 -> 5.10.2
* MockK 1.13.8 -> 1.13.11
* Dokka 1.9.10 -> 1.9.20
* AtomicFU 0.23.1 -> 0.24.0
* Binary compatibility validator 0.13.2 -> 0.15.0-Beta.2
* gradle-buildconfig-plugin 5.1.0 -> 5.3.5
* Foojay Toolchains Plugin 0.7.0 -> 0.8.0
* Replace gradle/gradle-build-action with gradle/actions/setup-gradle
* Replace gradle/wrapper-validation-action with gradle/actions/wrapper-validation

## House-keeping

* Update README (#915)
* Disable timeouts for Kotlin/JS tests (#926)
* Remove unused resource files (#935)
* Enable binary compatibility validation for KLibs (#929)
* Fix test related Gradle deprecation warnings (#936)
* Create `sourceLink` `URL` with non-deprecated `URI` constructor (by @SebastianAigner in #938)

# 0.13.1

This release fixes an exception when trying to deserialize `Permissions` contained in `GuildAuditLogEntryCreateEvent`s.
Kord expected to receive JSON strings while
[Discord is sending JSON numbers](https://github.com/discord/discord-api-docs/issues/6616).

See #911 and #912.

# 0.13.0

This release fixes a bug where the Spanish Latin America `Locale` (es-419) couldn't be deserialized correctly, so users
with that `Locale` couldn't interact with Kord bots via interactions.

## Additions

* Add `WebhookMessageCreateBuilder.appliedTags` (by @lukellmann in #899)

## Changes

* Bump `DeprecationLevel`s after 0.12.0 (by @lukellmann in #896)
* Remove deprecation from `User.discriminator` and `User.tag` (by @lukellmann in #901)
* Align `ArchiveDuration` with generated kord enums (by @lukellmann in #902)
* Deprecate `DiscordBitSetSerializer` and `Locale.Serializer` (by @lukellmann in #903)

## Fixes

* Support Spanish (Latin America) (by @gdude2002 in #906)

## Dependencies

Updated in #900

* Gradle 8.4 -> 8.5
* Kotlin 1.9.20 -> 1.9.21
* Ktor 2.3.6 -> 2.3.7
* kotlinx.serialization 1.6.1 -> 1.6.2
* kotlinx-datetime 0.4.1 -> 0.5.0
* kotlin-logging 3.0.5 -> 6.0.1
* Stately 2.0.5 -> 2.0.6
* KSP 1.9.20-1.0.14 -> 1.9.21-1.0.16
* KotlinPoet 1.15.1 -> 1.15.3
* AtomicFU 0.23.0 -> 0.23.1
* gradle-buildconfig-plugin 4.2.0 -> 5.1.0
* actions/setup-java v3 -> v4

# 0.12.0

## Additions

* Add interaction permissions to `MemberData` and `Member` (by @Tmpod in #884)
* Add `SelectDefaultValue`s (by @lukellmann in #881)
* Add `Permission.CreateGuildExpressions` and `Permission.CreateEvents` (by @lukellmann in #892)
* Add `StageInstanceCreateRequest.guildScheduledEventId` (by @lukellmann in #893)

## Changes

* Bump `DeprecationLevel`s (by @lukellmann in #879)
* Use debug log level for unknown gateway event names (by @viztea in #890)
* Add common `MessageBuilder` supertype (by @lukellmann in #891)

## Fixes

* Fix `DiscordAuditLogEntry.userId` nullability (by @lukellmann in #885)

## Dependencies

Updated in #883, #888 and #894

* Gradle 8.3 -> 8.4
* Kotlin 1.9.10 -> 1.9.20
* Ktor 2.3.4 -> 2.3.6
* kotlinx.serialization 1.6.0 -> 1.6.1
* Stately 2.0.2 -> 2.0.5
* KSP 1.9.10-1.0.13 -> 1.9.20-1.0.14
* KotlinPoet 1.14.2 -> 1.15.1
* JUnit 5 5.10.0 -> 5.10.1
* MockK 1.13.7 -> 1.13.8
* Dokka 1.9.0 -> 1.9.10
* AtomicFU 0.22.0 -> 0.23.0
* gradle-buildconfig-plugin 4.1.2 -> 4.2.0

# 0.11.0

## Additions

* Add interaction channel field (by @NoComment1105 in #810)
* Add `avatar_decoration` to user (by @NoComment1105 in #852)
* Add stage channel create functions (by @NoComment1105 in #856)
* Implement custom status (by @DRSchlaubi and @lukellmann in #857)
* Allow modifying `GuildMemberFlags` (by @lukellmann in #865)
* Add `RoleFlags` (by @lukellmann in #866)
* Add `AttachmentFlags` (by @lukellmann in #867)
* Add `MediaChannel`s (by @lukellmann in #853)
* Allow modifying `GuildOnboarding` (by @lukellmann in #819)
* Add `ReactionAddEvent.messageAuthorId` (by @lukellmann in #873)
* Add new `AuditLogEvent`s (by @lukellmann in #874)
* Add `with_counts` param for `GET` `/users/@me/guilds` (by @lukellmann in #875)
* Add `TeamMemberRole` (by @lukellmann in #876)
* Add `AuditLogEntryOptionalInfo.integrationType` (by @lukellmann in #877)

## Changes

* Bump `DeprecationLevel`s (by @lukellmann in #844)
* Generate bit flags (by @DRSchlaubi and @lukellmann in #766)
* Bring kord enum API closer to bit flags API (by @lukellmann in #861)
* Replace companion object serializers (by @lukellmann in #869)
* Remove type parameter from `Choice` (by @lukellmann in #868)

## Fixes

* Correctly close zlib stream when gateway disconnects (by @DRSchlaubi in #849)
* Fix usage of `BigInteger` in `DiscordBitSet.value` (by @lukellmann in #864)
* Fix deserialization of `DiscordApplication` (by @lukellmann in #871)

## Dependencies

Updated in #842, #859 and #872

* Gradle 8.1 -> 8.3
* Kotlin 1.8.21 -> 1.9.10
* Ktor 2.3.0 -> 2.3.4
* kotlinx.coroutines 1.7.1 -> 1.7.3
* kotlinx.serialization 1.5.1 -> 1.6.0
* kotlinx-datetime 0.4.0 -> 0.4.1
* kotlin-node 18.16.3-pre.546 -> 18.16.12-pre.619
* Stately 2.0.0-rc1 -> 2.0.2
* KSP 1.8.21-1.0.11 -> 1.9.10-1.0.13
* KotlinPoet 1.13.2 -> 1.14.2
* JUnit 5 5.9.3 -> 5.10.0
* MockK 1.13.5 -> 1.13.7
* SLF4J 2.0.7 -> 2.0.9
* Dokka 1.8.10 -> 1.9.0
* AtomicFU 0.20.2 -> 0.22.0
* Binary compatibility validator 0.13.1 -> 0.13.2
* gradle-buildconfig-plugin 4.0.4 -> 4.1.2
* Foojay Toolchains Plugin 0.4.0 -> 0.7.0
* actions/checkout v3 -> v4

## House-keeping

* Remove unnecessary `RedundantVisibilityModifier` suppression (by @lukellmann in #858)
* Don't use value class `Reset` with `AtomicRef` (by @DRSchlaubi and @lukellmann in #863)

# 0.10.0

## Additions

* Support new username system (by @lukellmann in #825)
* Add `Permission.UseExternalSounds` (by @lukellmann in #833)
* Add new error codes (by @lukellmann in #834)
* Add mention raid protection to Auto Moderation (by @lukellmann in #830)
* Add support for Application Role Connection Metadata (by @lukellmann in #836)
* Add support for join raid protection (by @lukellmann in #832)

## Changes

* Bump `DeprecationLevel`s (by @lukellmann in #821)
* Remove no longer needed pipeline interception (by @lukellmann in #824)
* Change `parentId` and `lockPermissionsToParent` to Optionals (by @Tmpod in #828)

## Fixes

* Fix deserializing embeds with `null` author url (by @lukellmann in #839)

## Dependencies

Updated in #826

* Kotlin 1.8.10 -> 1.8.21
* Ktor 2.2.4 -> 2.3.0
* kotlinx.coroutines 1.6.4 -> 1.7.1
* kotlinx.serialization 1.5.0 -> 1.5.1
* kotlin-node 18.14.0-pre.502 -> 18.16.3-pre.546
* KSP 1.8.10-1.0.9 -> 1.8.21-1.0.11
* KotlinPoet 1.12.0 -> 1.13.2
* JUnit 5 5.9.2 -> 5.9.3
* MockK 1.13.4 -> 1.13.5
* AtomicFU 0.20.0 -> 0.20.2
* Binary compatibility validator 0.13.0 -> 0.13.1
* gradle-buildconfig-plugin 3.1.0 -> 4.0.4

## House-keeping

* Simplify CI (by @lukellmann in #823)
* Use main as the permanent default branch (by @lukellmann in #831)

# 0.9.0

## Additions

* Support Kotlin/JS (by @DRSchlaubi and @Lukellmann in #775)
* Add support for voice messages (by @DRSchlaubi and @Lukellmann in #814)

## Changes

* Bump `DeprecationLevel`s (by @Lukellmann in #794)
* Replace `Icon` with `Asset` (by @oluiss and @Lukellmann in #703)

## Fixes

* Fix some `EntitySupplyStrategy` `toString`s being incorrect (by @GreemDev in #811)
* Fix List Nitro Sticker Packs endpoint (by @Lukellmann in #816)
* Fix `InstantInEpochMillisecondsSerializerTest` on JS (by @Lukellmann in #818)

## Dependencies

Updated in #783

* Gradle 8.0.2 -> 8.1

## House-keeping

* Add inspection for missing `@KordDsl` (by @DRSchlaubi in #800)
* Fix Qodana findings (by @Lukellmann and @DRSchlaubi in #812)
* Clean up (by @Lukellmann in #813)
* Improve `GenerateKordEnum` and `AnnotationArguments` (by @Lukellmann in #817)

# 0.8.3

## Additions

* Add `ApplicationFlag.ApplicationAutoModerationRuleCreateBadge` (by @NoComment1105 in #802)
* Add error code 50163 (by @NoComment1105 in #803)
* Add `Guild.maxStageVideoChannelUsers` (by @NoComment1105 in #804)
* Add guild onboarding (by @NoComment1105 and @Lukellmann in #805)

# 0.8.2

## Additions

* Add new permissions (by @NoComment1105 in #795) 

## House-keeping

* Add inspection for missing Optional default values (by @Lukellmann in #797) 

# 0.8.1

## Fixes

* Fix `ClassCastException` caused by `TextChannelThread.getParent()` (by @Lukellmann in #796)

# 0.8.0

## Additions

* Add forums (#684)
* Add new select menu types (by @oluiss in #707 and @Lukellmann in #721)
* Add `UserFlag.ActiveDeveloper` (by @oluiss in #720)
* Add new `GuildFeature`s and allow editing them (by @Lukellmann in #722)
* Add new error codes (by @Lukellmann in #723 and @NoComment1105 in #742 and #757)
* Add `Locale.INDONESIAN` (by @Lukellmann in #738)
* Add `KeywordAutoModerationRule.allowedKeywords` (by @Lukellmann in #731)
* Add support for nsfw commands (by @Lukellmann in #725)
* Add missing `MessageType`s (by @NoComment1105 in #744)
* Add `after` to audit log get (by @NoComment1105 in #745)
* Add support for gif stickers (by @NoComment1105 in #750)
* Add stage channel message types (by @NoComment1105 in #759)
* Add audit log entry create event (by @NoComment1105 in #751 and #761)
* Add missing integration events (by @NoComment1105 in #761, #763 and #764)
* Add guild member flags (by @NoComment1105 in #760)
* Add the ability to receive unknown events (by @DRSchlaubi in #769)
* Add `BlockMessageAutoModerationAction.customMessage` (by @Lukellmann in #774)
* Add silent messages and extend builders (by @DRSchlaubi in #762)
* Add Role subscriptions (by @NoComment1105 in #743 and @Lukellmann in #781)
* Add a nullable variant of `getAuthorAsMember` (by @NoComment1105 in #784)

## Changes

* Bump `DeprecationLevel`s (by @Lukellmann in #716)
* Deprecate `GuildFeature.PrivateThreads` (by @Lukellmann in #724)
* Stabilize `KordConfiguration` and `KordConstants` (by @Lukellmann in #753)
* Make `StageChannel` implement `TopGuildMessageChannel` (by @DRSchlaubi in #756)
* Deprecate `getGuild()` functions that call `getGuildOrNull()` under the hood (by @NoComment1105 in #728)
* Add bucket ID to the discovered bucket trace log (by @MrPowerGamerBR in #699)

## Fixes

* Generate `EncryptionMode` instead of using an enum (by @lost-illusi0n in #737)
* Fix nonce deserialization for big integers (by @Lukellmann in #765)
* Fix `MessageChannelBehavior.typeUntil` (by @Lukellmann in #768)
* Make `Snowflake`'s ordering consistent with `equals` (by @Lukellmann in #773)
* Fix various bugs in `DiscordBitSet` (by @Lukellmann in #772)
* Use 74 byte ip discovery packet instead of the deprecated 70 byte discovery packet (by @lost-illusi0n in #776)
* Fix breaking changes and bugs before release (by @Lukellmann in #793)

## Dependencies

Updated in #732, #739, #755, #782 and #788

* Gradle 7.5.1 -> 8.0.2
* Kotlin 1.7.20 -> 1.8.10
* KSP 1.7.20-1.0.8 -> 1.8.10-1.0.9
* Ktor 2.1.3 -> 2.2.4
* kotlinx.serialization 1.4.1 -> 1.5.0
* kotlin-logging 2.1.23 -> 3.0.5
* SLF4J 1.7.36 -> 2.0.7
* Dokka 1.7.20 -> 1.8.10
* AtomicFU 0.18.5 -> 0.20.0
* Binary compatibility validator 0.12.1 -> 0.13.0
* JUnit 5 5.9.1 -> 5.9.2
* MockK 1.13.2 -> 1.13.4

## House-keeping

* Use `libs.versions.toml` and clean gradle files (by @Lukellmann in #719)
* Clean up (by @Lukellmann in #730)
* Use AtomicFU compiler plugin (by @Lukellmann in #740)
* Fix CI badge in readme (by @DRSchlaubi in #741)
* CI updates and fixes (by @DRSchlaubi and @Lukellmann in #770, #778, #780 and #790)

# 0.8.0-M17

## Additions

* Add support for Auto Moderation (#647 #697 #713)
* Add error 240000 (#676)
* Add `ApplicationFlag.ApplicationCommandBadge` (#677)
* Parameter for deleting old messages in `GuildMessageChannelBehavior.bulkDelete` (#692)
* Add `application_commands` to audit log (#681)
* Add `UserPremium.NitroBasic` (#704)
* Make ephemeral messages deletable (#706)
* Add `Kord.getGuildOrNull` (#714)

## Changes

* Change attachment `InputStream` to `ChannelProvider` (#682)
* Deprecate `GuildFeature.Commerce` (#678)
* Update create guild ban endpoint (#679)
* Update voice state modification (#680)
* Use structured concurrency for `MessageChannelBehavior.withTyping` (#687)
* Generate kord enums with KSP (#686 #698)
* Use gateway url provided in `Ready` event for resuming (#666)
* Bump `DeprecationLevel`s (#688)
* Properly implement Identify rate limiting (#693)

## Fixes

* Fix gateway events created with `buildJsonObject` failing to be deserialized (#683)
* Fix `with_count` parameter typo (#690)
* Fix default avatar URL not working (#691)
* Make `LinearRetry` behave linearly for all inputs (#702)

## Dependencies

* Kotlin 1.7.10 -> 1.7.20
* Ktor 2.1.0 -> 2.1.3
* kotlinx.serialization 1.3.3 -> 1.4.1
* AtomicFU 0.18.3 -> 0.18.5
* Binary compatibility validator 0.11.0 -> 0.12.1
* Dokka 1.7.10 -> 1.7.20
* JUnit 5 5.9.0 -> 5.9.1
* MockK 1.12.5 -> 1.13.2

# 0.8.0-M16

## Breaking / Performance

* Events no longer implement `CoroutineScope` which caused a memory leak (#665 for migration steps)
* Bump deprecations (#653)

## Additions

* New error codes (#656 #655 #654)
* Add audit log reason to Modify Guild MFA Level endpoint (#668)
* Add events custom context (#667)
* Voice: Add helper to move/update voice connections (#657)

## Fixes

* Fix MessageStickerType constructor initialization deadlock (#670)

## Improvements / Updates

* Use suppressed exceptions for stack trace recovery (#658)
* Upgrade to Gradle 7.5.1 (#662)
* Changes to Kord's annotations (#659)

# 0.8.0-M15

## Additions

* Add various error codes (#644 #639 #637 #649)
* Add Kord Proxy Builder (#618)
* Add `Guild#cachedThreads` to fetch cachedThreads (#634)
* Add Missing string option length fields (#650)
* Add nsfw to voice channels create and modify requests (#642)
* Add app_permissions field (#646)
* Add Modify Guild MFA Level endpoint (#640)
* Add API version configuration (#601) 
* Add Voice text (#614)
* Snowflake destructuring (#609)

## Changes

* Update Message Type names (#645)
* Thread archive durations are no longer boost locked (#636)
* Improve RestClient's stacktrace recovery (#648)
* Update application command fields (#638)
* Remove audit log reason from Modify Guild Channel Positions endpoint (#641)
* Update Identify Connection Properties field names (#643)

## Fixes

* Fix nonce deserialization (#632)
* Voice: heartbeat nonce is zero (#619)
* Voice: voice connection dropping unexpectedly (#621)
* Voice: Fix typo in DefaultAudioPacketProvider declaration (#610)
* Use core event for MessageDelete in enableEvent (3dbb29f)

## Documentation

* Update docs for Message.Interaction.name (71b185e)

## Dependencies

* Binary compatibility validator 0.9.0 -> 0.10.1
* Kotlin 1.6.21 -> 1.7.10
* Dokka 1.6.20 -> 1.7.0
* AtomicFU 0.17.2 -> 0.18.2
* gradle-buildconfig-plugin 3.0.3 -> 3.1.0
* kotlinx-datetime 0.3.2 -> 0.4.0
* kotlinx.coroutines 1.6.1 -> 1.6.3
* kotlinx.serialization 1.3.2 -> 1.3.3
* kotlin-logging 2.1.21 -> 2.1.23
* Mockk 1.12.3 -> 1.12.4
* Ktor 2.0.0 -> 2.0.3


# 0.8.0-M14

## Changes

* Slash commands permissions v2 (#604)
* Add feature variant for voice (#608)
* Deserialize timestamps as Instant (#605)
* Update Channel Builders (#606)
* Use ktor Base64 functions (#600)
* Refactor Choice serializer (#598)
* Nullable user_limit (#602)
* Stricter Locale parsing (#597)

## Additions

* Add error 50080 (#607)

## Dependencies
* 
* Kotlin 1.6.20 -> 1.6.21
* BinaryValidator 0.8.0 -> 0.9.0

# 0.8.0-M13

## Changes

* Paginate getting bans (#585)
* Order locales like discord/discord-api-docs#4680 (#573)
* Update stage instance requests (#581)
* image_hash audit log change key (#578)
* Nullable channel name (#579)
* Make Optional a sealed class again (#588)
* Deprecate IntegrationApplication.summary (#580)
* Channel type GUILD_DIRECTORY (#583)
* Refactor common RateLimiter (#577)
* Deprecate nickname mentions (#590)
* Deserialize time as Duration (#586)

## Additions

* Add ANIMATED_BANNER feature (#584)
* Add strategy to mitigate loss of stacktrace through Ktors SuspendFunctionGun (#563)
* Add Application default authorization links and tags (#582)
* Add minValue and maxValue to ApplicationCommandOption (#572)
* Add Version constant injection (#576)
* Add support for slash command localizations (#570)
* Add guild_id to Interaction Data (#591)

## Fixes

* Fix conflict between property name and class discriminator (#595)
* voice: fix encryption buffer size (#568)
* Fix Guild Scheduled Event Gateway Events (#569)

## Dependencies

* binaryValidator: 0.6.0 -> 0.8.0
* Kotlin: 1.6.10 -> 1.6.20
* Gradle 7.4 -> 7.4.2
* AtomicFu 0.17.0 -> 0.17.2
* dateTime 0.3.1 -> 0.3.2
* coroutines 0.6.0 -> 0.6.1
* mockk 1.7.30 -> 1.7.36
* Ktor 1.6.7 -> 2.0.0

# 0.8.0-M12

## Changes

* As of 0.8.0-M12 Message Content Intent is required to receive message related events.
* Deprecate store channels (#564).
* Hotfix: revert nullable to optional changes in VoiceState (#567).
* nullable requestToSpeakTimestamp (#566).
* Fix oversights in #561 (#565).
* Discord docs updates (#540 #561).

## Additions

* User Agent header (#558 #562).
* Unsafe deferred responding (#557).
* Use gateway v10 (#554).
* Audit Log Change Key "type" to string values (#559).

# 0.8.0-M11

## Changes

* Switch to v10 for rest (#550)
* Invite and Application revamp (#530)
* Update enableEvent() (#553)
* Invite and Application revamp (#530)
* Revamp interaction implementations (#543 #533 #546)
* Documentation: clarify the usage of `Kord.restOnly`
* Update Permissions (#544)

## Additions

* Add selfVideo property (#545)

## Fixes

* Fix GuildScheduledEvents json representation and modify function (#549)

# 0.8.0-M10

## Additions

* Forms support (#531)
* Add support for attachment options in chat input interactions (#524)
* Add error 40060 40004(#532 #523)

## Fixes

* fix locale typos (#541)
* Add missing default value for strategy for getWebhookWithTokenOrNull (#539)

## Changes

* Change members resolved objects to DiscordInteractionGuildMember (#502)

## Dependencies

* Upgrade gradle to 7.4 and its wrapper

# 0.8.0-M9

## Fixes

* Fix .jpg not being detected (#458)
* Fix gateway not using provided threshold (#465) 
* Fix bug causing role PermissionOverwrites being added for members (#479)
* Fix Team.ownerUserId returning the wrong id (#509)
* Fix exception when choices are never set (#505 #512)
* Voice: fix race condition where heartbeat is sent before authentication (#511)

## Changes

* Allow providing  limit in AuditLogGetRequestBuilder (#477)
* Optional timestamp style (#516)
* No longer send Authorization header on endpoints without authorization (#450 #486)
* Suppliers and pagination logic refactor (#484)
* ComponentBuilders refactor (#494)
* Enable explicit API (#474)

## Additions

* Add mutes support (#448 #508)
* Add channel types in slash commands (#464)
* Add ActionInteractionCreateEvent (#456)
* Add autocomplete support (#456)
* Add disabled property to SelectMenuComponent(#492)
* Add limit to AuditLogGetRequestBuilder (#477)
* Add missing Webhook and Interaction functionality (#507)
* Add new JsonErrorCodes and fix existing ones (#482 #504 #501)
* Add new fields and parameters for scheduled events and invites (#518)
* Add new fields for attachments. (#506)
* Add interaction localization support

## Dependencies
* Kotlin: 1.5.10 -> 1.6.10
* KotlinxSerialization: 1.2.1 -> 1.3.2
* Coroutines: 1.5.0 -> 1.6.0
* Ktor: 1.6.0 -> 1.6.7
* AtomicFu: 0.16.1 -> 0.17.0
* Datetime: 0.2.1 -> 0.3.1
* KotlinLogging: 2.0.6 -> 2.1.21
* binaryValidator: 0.5.0 -> 0.6.0


# 0.8.0-M8


## Changes

* Embed description limit should be 4096 (#419)
* use behavior over entity in voice connect method (#428)
* rewrite frame interceptor (#427)
* Unify permission overwrite API (Fix #302) (#420)
* Make Snowflake.toString() more idiomatic, and deprecate .asString (#441)

## Fixes

* fix ButtonBuilder#emoji function (#431)
* Fix bom dependencies (#440)
* fix regression in the default frame interceptor (#443)
* Fix missing '=' in GuildBehavior.toString() (#442)

## Additions

* UserFlag and GuildFeature add-on (#422)
* Add support for receiving voice and opening up the voice api (#386)
* implement all encryption modes documented by discord (#424)
* explicit api for voice (#425)
* Old properties for Update events (#438)
* Add AutoComplete (#435)
* Implement Stage events (#421)

# 0.8.0-M7

## Additions

* Add `rtcRegion` to builders. (#413)
* Reintroduce `InteractionResponseBehavior#followUpEphemeral`

## Fixes

* Fix `IntChoice` not taking a  `Long`. (#414)
* Fix `InteractionBehavior#respondEphemeral` missing ephemeral flags. (#414)
* Fix target type of message command to `Message(Behavior)` instead of `UserBehavior` (#414)

# 0.8.0-M6

## Breaking

* `XBehavior#asX` now returns itself if the concrete type is already a complete entity. Use `XBehavior#fetchX` to always retrieve the most up-to-date version of an entity (#396)
* EphemeralBuilder builders have been unified with the persistent messages. (#397)
* Core events now accept a coroutineScope in the constructor (#391)
* Start thread methods have introduced a builder (#398)
* Shards have been moved to `dev.kord.gateway.builder` (#409)

## Changes

* Intents are now lazily evaluated (#409)
* Enable explicit api mode for core module (#406)
* Fixes and improvements for Snowflake (#370)
* Application commands improvements (#374 #384 #387)
* MasterGateway and Interceptors are switched into interfaces (#391)

## Additions

* Ephemeral files support (#397)
* Add missing invitable field (#398)
* Role icons support (#402)
* Per-Guild avatar support (#401)
* Add discord messaging timestamps (#385)
* Add named files and attachments (#379)
* Add missing avatar and username properties to `WebhookMessageCreateBuilder` (#376)

## Fixes

* Serialize NumberChoice as a Double, not as a String (#405)
* Sort threads as documented by discord (#411)
* Fix NPE on ThreadChannelDelete (#373)


# 0.8.0-M5

## Breaking

* slash commands and interactions have been redesigned to support the new command and interaction types.

## Changes

* Move SlashCommands functions to Kord. (#366)
* ApplicationCommands are now cached. (#366)
* Interaction events are split up into distinct events. (#366)
* Proper hierarchy for applications commands, interactions and their events. (#366)
* Rename `UsePrivate/PublicThreads` to `CreatePrivate/PublicThreads`. (#366)
* Include json error in exception message. (#369)

## Additions

* Experimental Voice support. #(363)
* Context support. (#366)
* Add `ResolvedObjects#messages` to resolve messages. (#366)
* Add `ChannelBehavior#of/OrNull` to safely get a typed channel. (#366)
* Add type safe arguments for chat input commands. (#366)
* Add SendMessagesInThread Permission. (#366)

## Fixes

* Ephemeral followups not being passed the ephemeral flags. (#368)
* Missing optional default values in some data types. (#362)
* incorrect serialization of `CommandArguement`. (#362)

# 0.8.0-M4

## Fixes

* Fixed the space in active threads get endpoint causing it to fail. (5dd3f380)
* Fixed incorrect serialization of `NUMBER` option. (#360)
* Fixed Missing properties in `MemberData`, `InteractionData` and others. (#361)

## Changes

* `Region` no longer has a `vip` property (5dd3f380)

# 0.8.0-M3

## Fixes

* Fixed Typo in ephemeral acks body causing acking to fail.

# 0.8.0-M2

## Fixes
* interaction acknowledgements no longer require data 
* Add SerialName for `InteractionApplicationCommandCallbackData#allowedMentions`

# 0.8.0-M1

## Additions

* Added support for threads. (#349 #358 #353 d1bf947)
* Added missing JSON error codes. (#347)
* Added support for slash command number type arguments. (#351)
* Added support for user banners. (#352)
* Added missing guild features. (d1bf947)

## Changes

* The `Channel` hierarchy has been changed to support threads. 
  Some behavior in `GuildChannel(Behavior)` and `GuildMessageChannel(Behavior)` has been removed to accommodate `ThreadChannel`s and 
  moved to `TopGuildChannel(Behavior)` and `TopGuildMessageChannel(Behavior)` respectively. (#353)

## Fixes

* Fixed missing audit log reasons on certain endpoints. (#346)


# 0.7.4

## Changes

* Promote user property in component interaction to a data object.

## Fixes

* Fixed `ComponentInteraction#user` throwing a `NullPointerException` when the interaction was created in a direct message.

# 0.7.3

## Additions

* Add StoreEntitySupplier.
* Add caching rest strategy.
* Add cache-rest caching strategy.
* Add select menus.

## Fixes

* Fix average ping conversion in `MasterGateway`.

## Changes

* Make `UpdateMessageInteractionResponseCreateBuilder` fields nullable.
* type in option builders is now private

## Breaking

* DiscordComponent
* InteractionCallbackData
* ApplicationInteractionData
* ComponentData
* CommandInteraction
* OptionsBuilder
* UpdateMessageInteractionResponseCreateBuilder


# 0.7.2

## Additions

* Allow adding a mentionable argument to commands

## Changes

* Make `Intent#values` a getter function.

## Fixes

* Mentionable arguments now correctly retrieve their entity.
* `Intent.values` emitting null when filtering. 

# 0.7.1

## Breaking

* `BaseInteractionResponseBuilder`
* `BaseInteractionResponseBuilder`
* `BaseInteractionResponseModifyBuilder`  
* `EphemeralInteractionResponseModifyBuilder`
* `PublicInteractionResponseModifyBuilder`
* `MessageModifyBuilder`
* `EditWebhookMessageBuilder`
* `InteractionResponseModifyRequest`
* `FollowupMessageBuilder`
* `PublicFollowupMessageModifyBuilder`
* `EphemeralFollowupMessageModifyBuilder`
* `PublicFollowupMessageCreateBuilder`
* `EphemeralFollowupMessageCreateBuilder`
* `FollowupMessageModifyRequest`
* `ComponentInteraction`

## Changes

* Message-related builders have been changed to accept `null` (for non-collections) and "empty list" (for collections)
when editing a message. This makes it possible to remove fields from a message without providing a substitution.
* `FollowupMessageBuilder` no longer has the `tts` field, since it does not apply to all its subclasses.

## Fixes

* `ActionRowComponent` properly returns its children.
* `ComponentInteraction#button` is now nullable as its documentation implies.

# 0.7.0

## Additions

* Implement voice stage channel (#239)
* Add "Competing" activity type (#272)
* Add unsafe application commands behavior (#281)
* Add buttons to Activity (#287)
* Add Message.applicationId (#289)
* Implement Stage instances (#291)
* Add Message interaction (#283)
* Add Ephemeral embed support (#296 #321)

## Changes

* Update deprecated message (#280)
* Sealed message types (#282)
* Improve slash command API and add support for components (#310 #294 #312 #324)
* Live entities can define a parent job (#304)

## Fixes

* Close InputStreams used for attachments (#309 #296)
* Make Updatestatus activities not-null (#274)
* Fix GuildUpdate core handling (#284)

## Performance

* Fix memory issues related to Permission combining (#277)

## Dependencies

* kotlin 1.4.32 -> 1.5.10
* kotlinxSerialization 1.1.0 -> 1.2.1
* ktor 1.5.2 -> 1.6.0
* kotlinxCoroutines = 1.4.2 -> 1.5.0
* kotlinLogging 2.0.4 -> 2.0.6
* atomicFu 0.15.1 -> 0.16.1
* binaryCompatibilityValidator 0.4.0 -> 0.5.0
* datetime 0.2.1

# 0.7.0-RC3

## Fixes

* Unhandled missing access when trying to get vanity url with the feature disabled. #264

# 0.7.0-RC2

## Additions

* Added slash commands support. #145 #201 #253 #249
* Added core representation of templates #136
* Added overloaded operations for Intents and Permissions. #152 #203
* Added welcome screens. #141
* Added `Kord#getInvite`. #143
* Added pending property to member. #153
* Added `Kord` functions to get webhooks. #232
* Added ability to send a message through request. #184
* Added extension methods for `LiveEntity`. #177
* Added `USE_SLASH_COMMANDS` permission. #208
* Added `Permission#values` and `Permissions#values`. #255
* Added allowed mentions. #256
* Added new webhook endpoints. #217
* Added missing error codes. #250
* Added `Message#messageReference`. #245

## Fixes

* Fix `GuildBehavior#getWidgetOrNull` #138
* Fix nullity in builders. #135
* Fix channelId nullity in UpdateVoiceState. #144
* Fix provider nullity in embeds. #151
* Fix WebhookType.Incoming incorrect value. #156
* Fix `DiscordErrorResponse` inability to consume full input #162
* Fix `MessageCreateEvent#withStrategy` returning `Strategizable`. #233
* Fix serialization issues for `DiscordActivityPartySize`. #168
* Fix `Attachment#isImage` check. #172
* Fix`rpc_origins` being nullable instead of optional. #173
* Fix `LiveMessage` not being shut down on bulk delete. #174
* Fix `Message#authorAsMember` throwing if guild was not found. #178
* Fix swapped `mute` and `deaf` in `VoiceStateData`. #188
* Fix `preview_asset` not being optional. #206.
* Fix parsing raw responses into Json. #205
* Fix typos in webhook and welcome screen routes. #219 #220
* Fix gateway 0 blocking other shard gateways from running. #194
* Fix unhandled unknown channel types. #251


## Changes

* Allow controlling the number of total shards #196
* Replaced invoke functions with top-level factory functions. #210
* Allow multiple file upload. #247 #228 #229
* Added missing contracts #243

## Dependencies

* kotlin 1.4.10 -> 1.4.32 #198
* kotlinx.serialization 1.0.0 -> 1.1.0 #198
* kotlinx.coroutines 1.4.0 -> 1.4.2 #198
* kotlinx.atomicfu 0.14.4 -> 0.15.1 #198
* kotlinx.binary-compatibility-validator 0.2.3 -> 0.4.0 #198
* ktor 1.4.1 -> 1.5.2 #198
* kotlin-logging 2.0.3 -> 2.0.4 #198

# 0.7.0-RC

## Additions

* Added support for `MessageSticker`. #119
* Added support for `RoleTags`. #119
* Added `GuildBehavior#getMembers`. #119
* Added the ability to move a channel under a category when moving channels. #119

## Fixes

* Fixed `MemberBehavior#edit`, now returning a member. #120 
* `Gateway#on` now allows suspending consumers.
* Fixed `GuildBehavior#editSelfNickname` incorrectly parsing the response json. #125
* Fixed getting user's avatar url. #128

## Changes

* `VoiceServerUpdateEvent#endpoint` is now nullable. #119
* **Moved com.gitlab.kord.common to dev.kord.common.** #122 
* **Moved com.gitlab.kord.rest to dev.kord.rest.** #122
* **Moved com.gitlab.kord.gateway to dev.kord.gateway.** #122
* **Moved com.gitlab.kord.core to dev.kord.core.** #122

## Removals

* Removed deprecated API from 0.6.x.

# 0.7.0-M2

## Additions

* Re-added `values`  in `Intent` and `Intents`.
* Added support for inline replies and `MessageBehavior#reply` to quickly create a reply to a message. #110
* Added a shortcut to create channels from a `CategoryBehavior`, giving them a parentId by default. #109 
* Added `Gateway#requestMembers` and `GuildBehavior#RequestMembers` as a shortcut for the `RequestGuildMembers` command.

## Fixes

* Fixed Color bug when converting from java.awt.Color with alpha. #114

## Changes

* Gateway reconnect retries reset on handshake. #68

# 0.7.0-M1

## Changes

* Updated API to Discord V8. #108
* Introduced Optionals in lower level API and core xData classes. #108 #95
* De-inlined Snowflake and implemented it into the lower level API. #108
* Rewrote `AuditLog` and its child classes and introduced them to to `core`. #108
* `Kord#events` is now a `SharedFlow` which can be configured via `KordBuilder#eventFlow`. #102 
* `Image` now supports image sizes that are common for Discord image resources. #98
* `java.awt.Color` has been replaced with `com.gitlab.kordlib.common.Color`. #5
* `core` Entities should have a meaningful `toString` representation. #88
* Request builders no longer have `lateinit` fields, these are now required arguments in the builder DSLs. #108
* `Permissions` and `Intents` now have more and easier constructors. #103

## Additions

* `RestRequestException` now holds a reference to an (optional) `DiscordErrorResponse` with a more specific error message and code.
* `PremiumTier` now has a `maxEmotes` field. #74
* Added a `getDmChannelOrNull` to `UserBehavior` to safely try and open a DmChannel with a user. #111

## Fixes

* `GuildBehavior#getVanityUrl` will now correctly return null when the guild does not have a vanity url.
* Voice channels can now change their topic. 
* Fixed `CacheEntitySupplier` not returning certain cached entities.

## Dependencies

* Kotlin 1.4.0 -> 1.4.10
* ktor 1.4.0 -> 1.4.1
* kotlinx.serialization 1.0.0-RC -> 1.0.0
* kotlinx.coroutines 1.3.9 -> 1.4.0
* kotlinLogging 1.7.10 -> 2.0.3


# 0.6.10

## Fixes

* Fixed `Guild#getVanityUrl` throwing an exception when a guild did not support vanity invites. #104
* Fixed `Embed#fields` always returning empty. #105

# 0.6.9

## Fixes

* Fixed `Rolebehavior#mention` for `everyone` roles. #96
* Fixed NPE being thrown when trying to query data types that were not cached.
* Fixed message content not being sent when uploading a file. #99

# 0.6.8

## Fixes

* Fixed rest action reasons not encoding properly. #86

# 0.6.7

## Fixes

* Fixed removed channels not being removed from cache. #84

# 0.6.6

## Fixes

* Fixed an issue where `Members` would not consider `Users` with the same ID equal.
* Removed a dependency on Java 10 introduced in 0.6.5. #78
* Fixed the event flow dropping events under too much pressure. #81
* Fixed the `KordCacheBuilder` ignoring configuration #82
 
# 0.6.5

## Fixes

* Fixed an issue where `LiveMessage` would not filter its event flow. #70
* Fixed an issue where emojis from events would be decoded incorrectly.

# 0.6.4

## Additions

* Added a `MemberBehavior#addRole` and `MemberBehavior#removeRole` variant which accepts an audit log message.

# 0.6.3

## Fixes

* Fixed GuildMessageChannelBehavior#bulkdelete  incorrectly deleting messages older than 14 days


# 0.6.2

## Additions

* Added a new `Field` builder function. #57
* Added `Kord#getChannelOf` to request a type of channel.

## Changes

* `name` and `value` default to empty space. 
* `PRESENCES_REPLACE` event will be ignored. #42

# 0.6.1 

## Additions

* Added `Team` and other properties to ApplicationInfo.

## Changes

* `ReactionEmoji.Unicode` now correctly compares on name for equality.

## Performance

* `CacheEntitySupplier#getGuildMembers` will no longer query MemberData on each user.
* Reduced the number of mappings inside suppliers.

## Fixes

* Fixed type mismatch when comparing guildId in `CacheEntitySupplier#getGuildMembers`


# 0.6.0

## Changes

* `Member#kick` and `Guild#kick` now have an optional reason.
* `KordBuilder` now throws a (more) useful exception when building a bot with an invalid token.
* The REST module will now use `discord.com/api` instead of the deprecated `discordapp.com/api`.
* Kord now uses `Dispatchers.default` as the default dispatcher.

## Fixes

* Fixed an issue where Invite events would not fire if the invited user didn't have an avatar.
* Fixed some outdated docs on the `KordBuilder`.
* Fixed an issue where voice states from guild creates were not getting cached.

## Additions

* Introduced an experimental REST-only variant of the Kord builder. This will automatically disable gateway and cache
related APIs and replace them with a no-op implementation.
* Introduced a no-op `Gateway` implementation.

## Performance

* Removed an unneeded REST call when building Kord.

## Dependencies

* kotlin 1.3.72 -> 1.4.0
* ktor 1.3.2 -> 1.4.0
* kotlinx.serialization 0.2.0 -> 1.0.0-RC
* kotlinx.coroutines 1.3.7 -> 1.3.9

# 0.5.11

## Fixes

* Fixed an issue where multiple voice states could be present per user per guild.
* Fixed an issue where presences would be incorrectly deserialized in guild member chunk events.
* Fixes member chunk events not caching presences.

# 0.5.10

## Fixes

* Fixed an issue with entity flows requested from REST duplicating entities.

# 0.5.9

## Fixes

* Fixed an issue where getting a channel from a guild would incorrectly throw an exception during the guild id check. 
(again)


# 0.5.8

## Fixes

* Fixed an issue where getting a channel from a guild would incorrectly throw an exception during the guild id check.

# 0.5.7

## Additions

* Added `BanAddEvent#getBan` to get the full ban object.
* Re-added `MessageCreateBuilder#allowedMentions` after removal in 0.5.0.

# 0.5.6

## Fixes
* Fixed incorrect calculations of denied `Permissions`. 

# 0.5.5

## Additions

* Added `MessageBehavior#publish` to publish a message in an announcement channel.
* Added `NewsChannelBehavior#follow` to follow an announcement channel in another text channel.

## Fixes

* Fixed `GuildChannel#getEffectivePermissions` not correctly denying permissions denied for the user specifically.

# 0.5.4

## Additions

* Added `GuildBehavior#getChannel`, `GuildBehavior#getChannelOf` and their nullable variants.

## Deprecations

* `GuildBehavior#unBan` has been deprecated for `GuildBehavior#unban`.

# 0.5.3

## Fixes

* `getGuildMembers` returns the correct limit for both Cache and Rest suppliers.

# 0.5.2
## Additions
* Add missing mention property for unicode emojis.
* Re-add `guildId` to `Invite` for compatibility.

# 0.5.1

## Additions
* Added `PartialGuild` in `Invite`
* Added `GuildBehavior.createEmoji`
* Added `GuildEmoji.delete` and `GuildEmoji.edit`

## Fixes

* `DiscordInvite#targetUser` is now correctly nullable.
* `PermissionOverwriteEntity#getGuildOrNull` uses the correct supplier method.
## Changes
* `Invite` now uses a `Channel` instead of `GuildChannel`.
# 0.5.0

## Additions

* `mention` properties for `GuildEmoji` and `ReactionEmoji`

# 0.5.0-rc2

## Additions

* Added [Gateway Intents](https://github.com/discordapp/discord-api-docs/blob/feature/gateway-intents/docs/topics/Gateway.md#gateway-intents), allowing users to filter events send by Discord. #60
* Added `VIEW_GUILD_INSIGHTS` permission #88
* Added `MessageCreateEvent#guildId` to replace the removed `Message#guildId`.
* Added `MessageCreateEvent#member`.

## Removals

* Removed deprecated API from 0.4.x

## Dependencies

* kotlin 1.3.70 -> 1.3.72
* ktor 1.3.1 -> 1.3.2
* kotlinx.coroutines 1.3.4 -> 1.3.7
* kotlin-logging 1.7.8 -> 1.7.10

# 0.5.0-rc1

## Performance

* Getting entities from a flow of non-cached entities should be considerably faster.

## Fixes

* non-final socket closures use 4900 instead of 1000.

## Additions

* Added the `EntitySupplyStrategy`, entities will now keep a reference to 
a `EntitySupplier` (fetched from the strategy) from which they'll be able to fetch other entities (`getX` methods). #74
* Added `withStrategy(EntitySupplyStrategy)` to change the `EntitySupplier` of most entities. #74
* Added a `CacheEntitySupplier` and `RestEntitySupplier` supplier that exclusively operates on Cache and REST
respectively, as well as a strategy that prioritizes Cache over REST like previous versions. #74
* Added `getXOrNull` variants to fetching entities that won't explode when trying to get an entity that doesn't
exist. #74

## Changes

* Changed `GuildCreateBuilder` to be more inline with recent api changes. #77
* `core` Event constructors are no longer internal.
* `Kord#gateway` is now a `MasterGateway`, exposing all sharded gateways #65
* `core` Events now expose their shard index as well as the `Gateway` they were spawned from. #65
* `DisconnectEvent` and `Close` have been extended with more detailed implementations #65
* `Gateway` now accepts a `PresenceBuilder` to configure its original presence. #72
* Rest Discord API version can now be configured by setting the `com.gitlab.kordlib.rest.version` system property, `v6` by default.
* `DefaultGateway` now supports zlib compression and enables it by default.

# 0.4.22

This release contains breaking changes related to webhooks.

## Additions

* Added `WebhookBehavior#executeIgnored` which does not wait for the message to be processed.

## Changes

* `WebhookBehavior#execute` will now return a `Message`.

## Fixes

* Fixed an issue when deserializing a Webhook would throw an exception.
* Fixed an issue where endpoints returning nullable types would throw an exception.

# 0.4.21

## Fixes

* Fixed cache not removing messages deleted from a `MessageDeleteBulk`.

# 0.4.20

## Additions

* Added error codes 10026(Unknown ban), 40002(You need to verify your account in order to perform this action) and
30015(Maximum number of attachments in a message reached (10)) to the `JsonErrorCode`.
* Added `approximate_member_count` `approximate_presence_count` to guilds, which will be present when requesting a guild
through rest.
* Added missing `DmChannel#recipientBehaviors`.
* Added missing `MessageUpdateEvent#message`, `MessageUpdateEvent#channel`, `MessageUpdateEvent#getMessage`,
`MessageUpdateEvent#getChannel`.
* Added missing `PresenceUpdateEvent#member`, `PresenceUpdateEvent#guild`, `PresenceUpdateEvent#getUser`,
`PresenceUpdateEvent#getMember`, `PresenceUpdateEvent#member`, `PresenceUpdateEvent#getGuild`.
* Added `chunk_index` and `chunck_count` properties to `GuildMembersChunkData`.
* Added `Invite#targetUserType`.
* Added `User#flag`.
* Added `GuildFeature.WelcomeScreenEnabled`.
* Added `MessageModifyBuilder#allowedMentions`.
* `Embeds` can now copy their contents over to builders by using `Embed#apply(EmbedBuilder)`.
* Added `User#premiumType`.
* Added `GuildPreview` and the ability to get previews for public guilds via `Kord#getGuildPreview`.

## Fixes

* Fixed `MessageModifyBuilder` ignoring flags.


# 0.4.19

## Fixes

* Fixed an issue where `ClientStatus` would only display the desktop status.

# 0.4.18

## Fixes

* Fixed an issue where presences from guild creates were cached without guild id.

# 0.4.17

## Fixes

* Fixed REST throwing an exception when parsing an error without code.

# 0.4.16

## Changes
* Behaviors have been removed from VoiceState due to lack of guildId.

## Fixes
* Unmatched data structure between VoiceState and its data.
* ISO_INSTANT not being used to format and Instant object.

# 0.4.15

## Changes
* Classes implementing `Entity` now correctly implement equals and hashcode based on ids.

# 0.4.14

## Fixes
* Fix `GuildMessageChannelBehavior#bulkDelete` manually deleting messages younger than 14 days and trying to bulk delete messages 
older than 14 days, instead of the other way around. 

# 0.4.13

## Fixes
* Fix guild emojis not having their correct id.

# 0.4.12

## Fixes
* Fix unexpected data fields throwing exceptions when parsing `Gateway` `Events`. This should now be limited to
unknown opcodes only.

# 0.4.11

## Fixes
* `ParallelRequestRateLimiter` will no longer try to unlock a mutex twice on a error response

# 0.4.10
## Fixes
* `DiscordErrorResponse` incorrect serialization

# 0.4.9

ID collections in modify builders have undergone a breaking critical bug fix.
## Additions
* Added `JsonErrorCode` and `DiscordErrorResponse` to map Discord's Json error messages.

## Changes
* Added `error` field to `KtorRequestException` to include `DiscordErrorResponse`   
## Fixes

* Fixed `permissionOverwrites` in `TextChannelModifyBuilder`, `VoiceChannelModifyBuilder`, `NewsChannelModifyBuilder` being final.
* Fixed `roles` in `EmojiModifyBuilder` and `MemberModifyBuilder` being final.

# 0.4.8

## Additions

* Added Integrations.
* Guilds can now request their own Integrations with `GuildBhehavior#integrations`.
* Added `preferredLocale` and `publicUpdatesChannelId` to `Guild` and `GuildModifyBuilder`.
* Added some utility functions to the `KordCacheBuilder`.
* Added `GuildDiscoveryDisqualified` and `GuildDiscoveryRequalified` to `MessageType`. #79

## Changes

* `KtorRequestHandler` will now log the body of requests and responses.

## Fixes

* The GuildService now returns the correct type of integration objects.
* Fixed a typo in the `Embed#type` property kdocs.
* Fixed an issue where paginated flows would emit duplicate items.

## Deprecations

* `Embed#type` has been deprecated. #80
* `LiveNewsChannel`, `LiveStoreChannel` and `LiveTextChannel` have been deprecated. Message channels in guilds can 
change type during their lifetime, which means type can't be guaranteed. `LiveGuildMessageChannel` has been introduced as
an alternative.

# 0.4.7

## Fixes

* Fixed an issue where editing a guild category would reset permissions.
* Fixed an issue where editing a guild emoji would reset permissions.
* Fixed an issue where editing a guild member would reset permissions.

## Removals

* Removed some `Kord` functions that fetched non 'top-level' entities. Kord is no longer
the central source for getting entities and these changes try to reflect that. #74
You should use the new entity suppliers for those instead. #74
* `KordCache` has been removed, Kord now keeps a reference to a generic cache instead.
You can still get similar behavior using `kord.with(EntitySupplyStrategy.cache)`. #74


# 0.4.6

## Additions

* Added `Guild#memberCount`.
* Added `GuildEmoji#isAvaiable`. #84
* Added allowed mentions to message create. #83


## Changes

* `MessageChannel#withTyping` should now properly stop when cancelling the coroutine context

## Fixes

* Fixed channels cached in guild create events not having a guild id.
* Fixed `DiscordCreatedInvite#maxUses` serialization typo.
* Fixed an issue where editing a guild channel would reset permissions.

# 0.4.5

## Additions

* Added `Member#roleBehaviors`
* You can now add or remove entire `Permissions` to/from the `PermissionsBuilder`
* Added `Member#isOwner`
* Added `Member#getPermissions`
* Added `Message.isPinned`
* Added `GuildChannel#getEffectivePermissions`

## Changes

* `Message#guildId` and `Message#guild` are deprecated due to inconsistent availability.
* removed `ReactionEmoji.id` due to compiler issues regarding nullable inline classes, check for Custom type instead.

## Fixes

* Guild emojis update correctly on `GuildEmojisUpdate` event.
* Ratelimiters should no longer lock up when throwing an exception during requests.

# 0.4.4

## Additions

* Added `MessageBehavior#withTyping`.

## Changes

* usage of `kotlinx.io.inputstream` has been replaced with `java.io.inputstream` following the internalization
of the typealias.

## Dependencies

* kotlin 1.3.61 -> 1.3.70
* kotlinx.serialization 0.14.0 -> 0.20.0
* kotlinx.coroutines 1.3.3 -> 1.3.4

# 0.4.3

## Additions

* Added `Guild#roleBehaviors`.

## Fixes

* Fix incorrect deserialization of mentioned roles in messages.
* Message updates now correctly update mentioned channels.

# 0.4.2

## Additions

* Added `GuildBehavior.getRole`.
* Added missing `Guild.channelIds` and `Guild.channelBehaviors`.

# 0.4.1

## Additions

* Added a `CategoryCreateBuilder` to `GuildBehavior`. #67

## Fixes

* Removed `url` from `EmbedFooterRequest`, as it's not an actual field in the Discord API.  #66

# 0.4.0

## Additions

* `Kord` and its`Cache` now implement a common interface `EntitySupplier` to retrieve entities that can be cached.  #54
* `mentionedRoleIds`, `mentionedRoleBehaviors`, `mentionedUserIds`, `mentionedUserBehaviors` were added to `Message`.
* Introduced two implementations for the `RequestRateLimiter`: `ExclusionRequestRateLimiter` and `ParallelRequestRateLimiter`, 
which will be replacing the `ExclusionRequestHandler` and `ParallelRequestHandler` respectively. #59

## Changes

* All fields but `name` are now optional in `GuildCreateBuilder` and `GuildCreateRequest`. #62
* Removed the `ExclusionRequestHandler` and `ParallelRequestHandler` and introduced the `KtorRequestHandler`, which accepts any `RequestRateLimiter`. #59
* `Message#mentionedRoles` and `Message#mentionedUsers` now return a `Flow` of their respective entities instead of a `Set<Snwoflake>`.
* `StoreChannel#edit`, `TextChannel#edit` and `NewsChannel#edit` now supply their builder as a receiver.
* core entity builders were moved from `com.gitlab.kordlib.core.builder` to `com.gitlab.kordlib.rest.builder` and are now
part of the rest module.
* `Snowflake` was moved to the common module from core. #53
* `Kord#getRegions()` was deprecated for `Kord#regions`.
* `Kord#getUsers()` was deprecated for `cache#users`.
* various Snowflake argument names have been changed in`Kord` to better reflect the entity they represent.
* A reified `getChannel` has been added to `EntitySupplier` that will try to cast the channel to the given type.
* `CategoryModifyBuilder#permissions` is now a `val`.
* `ChannelPermissionModifyBuilder` is now a proper `AuditRequestBuilder`.

## Fixes

* fixed typo `CategoryModifyBuilder#positon` -> `CategoryModifyBuilder#position`

# 0.3.3

## Fixes

* Fixed `guild-id` being wrongly deserialized as `guildId` in `DiscordAddedGuildMember`.

* Fixed an issue where disconnecting from the `DefaultGateway` 
without closing the connection (i.e. dropping your internet connection) would indefinitely suspend the `DefaultGateway`,
making it unusable.

# 0.3.2

## Additions

* Added `InviteCreate`, `InviteDelete` an `MessageReactionRemoveEmoji` events. #61
* Added `deleteAllReactionsForEmoji` to ChannelService. #61

## Fixes 

* Fixed an issue where `DiscordInvite` was wrongly representing `inviter` as a `String` instead of a `DiscordUser`.

## Dependencies

* ktor 1.3.0-rc2 -> 1.3.0

# 0.3.1

## Fixes 

* Fixed an issue with Kord ignoring cached entries that relied on querying data by id. *again*.

# 0.3.0

> This version contains an upgrade of ktor that brings breaking changes, be sure to check out ktor's changelog if you
> were interacting with ktor or the rest module directly.
> 
> This change also comes with the removal of kotlinx.io, which was a transitive dependency. If your code relied on kotlinx.io
> consider manually including the dependency or migrating away from it entirely.

## Changes

* `Kord#getGuilds()` has been replaced with the non-suspending `Kord#guilds`.
* `@KordBuilder` has been renamed to `@KordDsl`.
* `KordClientBuilder` has been renamed to `KordBuilder`.
* `fileName` has been renamed to `filename`.
* `DefaultGateway`'s constructor accepts a single `DefaultGatewayData` instead of multiple properties.
* `DefaultGateway` is now able to rate limit identify attempts and accepts a `RateLimiter` that can be shared between multiple gateways. 
This will be done by default for Kord clients now.
* `KordClientBuilder`'s `gateway` function has been renamed to `gateways`. It now gives a list of shards and requests a list of gateways, this change
allows you to more easily share configuration between gateways.
* Emojis now have nullable names, this only appears when interacting with guild emojis that have been deleted.
* Rest, Gateway and Common entities have gained a `Discord` prefix to reduce name collisions with Core.
* `ParallalRequestHandler` has been upgraded to stable.
* `features` in `Guilds` are now represented as enum values instead of Strings. 

## Additions

* Added `LiveEntity` and its implementations to Core. These are self-updating entities that contain a filtered
event stream, only emitting related events.
* Added `targetUser` and `targetUserType` to invite creation. #47
* Added a `rules channel`, `SystemChannelFlags` and `discoverySplash` to `Guild`. #48
* Added `premium since` to `Member`. #45
* Added `inviter` to `Invite`. #44

## Fixes

* Ending the process while enabling the shutdownHook and without logging in causes UninitializedPropertyAccessException #50

## Dependencies 

* gradle 5.4 -> 6.0.1
* kotlin -> 1.3.60 -> 1.3.61
* kotlinx.serialization 0.13.0 -> 0.14.0
* ktor 1.2.5 -> 1.3.0-rc2
* kotlinx.coroutines 1.3.2 -> 1.3.3
* kotlin-logging 1.7.6 -> 1.7.8

# 0.2.4

## Additions

* `uses` has been added as a nullable property to `InviteResponse` .
* Added `mentionedChannel`-related fields to `Message`.
* Added `KordClientBuilder#enableShutdownHook`, which enables a shutdownHook that automatically closes the gateway on process exit.

## Changes

* `User.Avatar#getUrl` no longer returns `null` when requesting a static version of a user's animated avatar.

## Fixes

* Fixed an issue where `PartialEmoji` would not deserialize with a missing `id`.
* Fixed an issue where subscribing to the `events` Flow while kord was already logged in caused it to emit old events.
* Fixed an issue where `DefaultGateway` would stop reading payloads after throwing an Exception while parsing json.

# 0.2.3

## Additions

Enums now have an `Unknown` value to mitigate the effects of unannounced discord changes moving forward. [#39](https://gitlab.com/kordlib/kord/issues/39)
* `nicknameMention` has been added to `MemberBehavior`

## Changes

* `Flow` extension now support suspending functions

## Fixes

* `MessageCreateBuilder#addFile` no longer ignores files added.
* `GuildMembersChunkData#presences` has become nullable.
* `RequestGuildMembers#query` is no longer nullable.
* Fixed an issue with Kord ignoring cached entries that relied on querying data by id.
* `User#discriminator` and `User#tag` will now properly format discriminators with leading spaces.

## Dependencies
* kotlin-logging: 1.7.6
* kotlinx.coroutines: 1.3.2
* kotlinx.serialization 0.13.0
* ktor 1.2.5

# 0.2.2

## Additions

A new `RequestHandler`, the `ParallalRequestHandler` has been introduced as a preview feature. Compared to the 
`ExclusionRequestHandler`, this handler offers increased parallelism by allowing requests with different identifiers
to be handled in parallel. The drawback is that this opens a small window for exceeding the global rate limit.

`Gateway` now has a `ping` field, containing the duration between the latest heartbeat and heartbeat ack.
`GuildModifyRequest` now has an optional `banner` field, which can contain a `base64 16:9 png/jpeg image for the guild banner (when the server has BANNER feature)`.
Added `presences` and `userIds` to the `RequestGuildMembers` class and the equivalents to `GuildMembersChunkData`.

## Removals

`Invite#revoked` has been removed since it [never existed](https://github.com/discordapp/discord-api-docs/commit/70390b75377098204ccda75e3a7240a1604c7639).

## Fixes

`filename` is now correctly deserialized for `Attachment` objects.

# 0.2.2

## Additions

`Gateway` now has a `ping` field, containing the duration between the latest heartbeat and heartbeat ack.

# 0.2.1

This is the first maintenance update for Kord 0.2. 
With it, we have started hosting Kord on bintray, check our README on what to include to get the newest version.

## Additions

* Added `Flow<T: Any>.firstOrNull` and `Flow<T: Any>.any` as their behavior is often needed when interacting with
flows of members, channels, etc (and really, they should've been part of the coroutines api).
* Added `isSelfSteaming` to `VoiceState`, indicating when a user  is streaming using "Go Live".

## Changes

* `KordClientBuilder` now allows you to pass a custom `CoroutineDispatcher`.
* Since most suspending calls in Kord will be IO related, `Kord` now uses `Dispatchers.IO` as its `CoroutineDispatcher`.
* `StoreChannel` can no longer be used to read or send messages. [discord api](https://discordapp.com/developers/docs/resources/channel#channel-object-example-store-channel).
* `NewsChannel` and `StoreChannel` have been upgraded to the stable api and are no longer in preview.
* `ExclusionRequestHandler` now takes request buckets into consideration.

## Fixes

# 0.2.1

This is the first maintenance update for Kord 0.2. 
With it, we have started hosting Kord on bintray, check our README on what to include to get the newest version.

## Additions

* Added `Flow<T: Any>.firstOrNull` and `Flow<T: Any>.any` as their behavior is often needed when interacting with
flows of members, channels, etc (and really, they should've been part of the coroutines api).

## Changes

* `KordClientBuilder` now allows you to pass a custom `CoroutineDispatcher`.
* Since most suspending calls in Kord will be IO related, `Kord` now uses `Dispatchers.IO` as its `CoroutineDispatcher`.
* `StoreChannel` can no longer be used to read or send messages. [discord api](https://discordapp.com/developers/docs/resources/channel#channel-object-example-store-channel).
* `NewsChannel` and `StoreChannel` have been upgraded to the stable api and are no longer in preview.

## Fixes

# 0.2.0

## Additions

* Added the `core` module, a wrapper around `gateway` and `rest` that introduces caching using our `cache` module.
As with all our api, it's not stable yet and we will probably continue to introduce breaking changes to improve the 
general look and feel and fix design flaws.

* Along with `core` comes the concept of entity `Behaviour`, 
which are stripped down discord entities (mostly only retaining their id) that are able to interact with rest on a
higher level than the `rest` module exposes. This is specifically geared towards users who have disabled caching, but
its use should be preferred towards anyone who doesn't want to risk increased cache hits or rest calls.

* `Gateways` now come with a `detach` function, which will allow implementations to (permanently) shut down and release
all resources. `DefaultGateway` didn't require this, but other implementations that use e.g. thread pools can now shut
those down in here. 

* `DefaultGateway` now comes with a builder dsl that has sane defaults.

* `ExclusionHandler` now comes with a secondary constructor that accepts a token.

## Changes

* Kotlin's experimental `Duration` has replaced `Long` typed arguments that represented durations in milliseconds. The previous
functions/constructors have been marked with `@Deprecated` and should be replaced with the new ones.

## Fixes

* Numerous nullability fixes and other inconsistencies with/because of the discord api.

# 0.1.0

## Additions

* Added the `rest` module, a direct mapping of Discord's REST API with rate limiting
* Added a common module, containing shared code between rest and gateway 
* Preview and Experimental annotations

## Changes

* Moved shared json classes to common
* Removed Snowflake from common and gateway

## Fixes

* guildId field has been renamed to id in GuildIntegrations
* The color field in Embed is now optional
* The timestamp filed in Embed is now optional
* The All Permission now correctly represents all permissions
* Missing fields have been added to GuildIntegrations
* DefaultGateway should now correctly reconnect on reconnect events
* DefaultGateway should no longer delay on user invoked close
