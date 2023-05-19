# jctypealias

## About
When I write apps using Jetpack Compose, I often find myself writing callbacks or lambdas from low-level to high-level composables. I realized that this could be simplified by creating a typealias for myself. This helped me to reduce the amount of callback writing and made my code faster to write. I decided to share this improvement by creating a repository that other developers can use.

## Usage
copy this [file](https://github.com/bayu07750/jctypealias/blob/main/lib/src/main/java/com/bayu/jctypealias/JC.kt) to your project 
```kt
// BEFORE
@Composable
@Composable
fun BottomSheetScaffold(
    uiState: HomeUiState,
    sheetState: SheetState,
    onAddNoteBtnClicked: () -> Unit,
    onEditNoteClicked: (Note) -> Unit,
    onDismissBottomSheet: () -> Unit,
    modifier: Modifier = Modifier,
    content: @Composable (PaddingValues) -> Unit,
) { }

// AFTER
@Composable
fun BottomSheetScaffold(
    uiState: HomeUiState,
    sheetState: SheetState,
    onAddNoteBtnClicked: JCallback,
    onEditNoteClicked: JCallbackType<Note>,
    onDismissBottomSheet: JCallback,
    modifier: Modifier = Modifier,
    content: @Composable (PaddingValues) -> Unit,
) { }


@Composable
fun HomeScreen(
    uiState: HomeUiState,
    onNoteClicked: JCallbackType<Note>,
    onAddNoteBtnClicked: JCallback,
    onDismissBottomSheet: JCallback,
    onEditNoteClicked: JCallbackType<Note>,
    modifier: Modifier = Modifier,
) { }
```

## Find this useful?
give star ⭐