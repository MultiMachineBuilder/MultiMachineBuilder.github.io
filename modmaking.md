---
layout: page
title:  "Write a mod"
categories: help
---
## Project setup
1. Create a new Java project in your IDE
2. Add Maven to your project
3. Set up `pom.xml`
4. Paste following code into dependencies:
```xml
	<dependency>
		<groupId>com.google.code.findbugs</groupId>
		<artifactId>annotations</artifactId>
		<version>3.0.1u2</version>
	</dependency>
	<dependency>
		<groupId>com.google.guava</groupId>
		<artifactId>guava</artifactId>
		<version>31.1-jre</version>
	</dependency>
	<dependency>
		<groupId>com.fasterxml.jackson.core</groupId>
		<artifactId>jackson-databind</artifactId>
		<version>[2.14.0-rc1,)</version>
	</dependency>
	<dependency>
		<groupId>com.fasterxml.jackson.core</groupId>
		<artifactId>jackson-core</artifactId>
		<version>2.13.2</version>
	</dependency>
	<dependency>
		<groupId>com.fasterxml.jackson.core</groupId>
		<artifactId>jackson-annotations</artifactId>
		<version>2.13.4</version>
	</dependency>
	<dependency>
		<groupId>com.github.Fylipp</groupId>
		<artifactId>easy-events</artifactId>
		<version>v1.1.0</version>
	</dependency>
```
5. Place content at specific directories:
    * `textures/` - textures
	* `sound/` - sounds
6. Place translations in a known directory (used in step 7)
7. Create several classes:
    * A class which implements `AddonCentral`, a class which defines mods
	* A class with items/blocks (this is a separate class to ensure that items are created at the right time)
	* A class with recipes (this is a separate class to ensure that recipes are created after items)
8. Fill in the methods:
    * (constructor) - instantiate mod
	* `info()` - return an instance of `ModMetadata` with mod name, release date, description and name
	* `firstOpen()` - load your translations with `GlobalSettings.injectResources()`
	* `makeContent()` - place your call to init function of your items class
	* `integrationModules()` - place your call to init function of your recipes class, and any mod integration
9. Create blocks and items.
    * If you want to create a block entity, implement any of these:
	    * `BlockEntityDataless` - when your block does not store any extra information beyond its type
		* `BlockEntityData` - if your block stores data and can't be rotated
		* `BlockEntityChirotable` - if your block can be rotated and flipped
		* `SkeletalBlockEntityRotary` - if your block can rotate, but not flip
	* If you want to create an item entity, implement `ItemEntity` if you want an immutable item,
	or `ItemEntityMutable`, if your item would be mutable.
	* If your item or block is an entity, declare an appriopriate entity type in your content class
	* If your item entity is immutable, declare `hash0()` and `equal0()` for equal items to collate.
	* If you want captions (titles and descriptions) to be translated, instead of a literal string, use a translation key.
	Translation keys begin with '#' and are followed by a key in your translation file.
	* Create additional classes if needed
10. Create recipes
	* If your recipe outputs an item entity, declare a raw item with `ItemRaw.make()` instead of an item entity as the recipe output.
	* Do not consume item entities within recipes
11. Test your mod. If you find bugs, debug them and apply fixes
12. Publish your mod to GitHub. (See [here](/contribute.html))
13. Write about your mod at [the game discussions](https://github.com/MultiMachineBuilder/MultiMachineBuilder/discussions) under 'Show and tell'