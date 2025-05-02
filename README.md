# Item Decoration
This repository is a great starting point for developers looking to enhance their skills while building practical tools for layout customization. 
While currently supporting only linear and grid layouts, it offers a solid foundation for further expansion and experimentation.
# Install
#### Step 1: Add the JitPack Repository
In your root `settings.gradle` file, add the JitPack repository at the end of the `repositories` block:

```gradle
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        mavenCentral()
        maven { url 'https://jitpack.io' }
    }
}
```

---

#### Step 2: Add the Dependency
In your module-level `build.gradle` file, add the following dependency:

```gradle
dependencies {
    implementation 'com.github.cherriedy:item-decoration:Tag'
}
```

Replace `Tag` with the specific version or tag of the library you want to use.

---

#### Step 3: Sync Your Project
After making these changes, sync your project in your IDE (e.g., Android Studio) to download and integrate the library into your build.
# How to use
Create corresponding `Strategy` class for `LinearLayoutManager` or `GridLayoutManage`, then apply to `SpacingItemDecoration`
### For `LinearLayoutManager`
If you want to add spacing for all directions and not including the spacing from the edge of `RecyclerView`:
```java
SpacingStrategy spacingStrategy = new LinearSpacingStrategy(requireContext(), 8, false);
binding.recyclerView.addItemDecoration(new SpacingItemDecoration(spacingStrategy));
```
If you want to choose which direction to add spacing:
```java
SpacingStrategy spacingStrategy =
  new LinearSpacingStrategy(requireContext(),
                        8,  EnumSet.of(Direction.LEFT, Direction.RIGHT, Direction.BOTTOM), false);
binding.recyclerView.addItemDecoration(new SpacingItemDecoration(spacingStrategy(=));
```
### For `GridLayoutManager`
```java
SpacingStrategy spacingStrategy = new GridSpacingStrategy(requireContext(), 8);
binding.recyclerView.addItemDecoration(new SpacingItemDecoration(spacingStrategy));
```
