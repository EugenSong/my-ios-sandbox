Protocol-Delegate Pattern
=========================
In the protocol-delegate pattern, one object (the delegate) acts on behalf of, or in coordination with, another object (the delegating object). The delegating object holds a reference to the delegate and sends messages to it when it needs to perform a task or request information. The delegate then performs the task or provides the information as needed.

Example in Swift
--
Let's say we have a little robot named R2-D2 and we want to make an app to help him navigate through a maze. The app will have a MazeViewController that displays the maze on the screen and allows the user to control R2-D2's movements.

However, we don't want the MazeViewController to be responsible for storing the information about the maze itself. Instead, we want to use a separate object to store that information and provide it to the MazeViewController when needed.

To do this, we can use the protocol-delegate pattern. First, we'll create a protocol called MazeDataProvider that defines the methods that the delegate object will need to implement. This might look something like this:

```swift
protocol MazeDataProvider {
  func numberOfRowsInMaze() -> Int
  func numberOfColumnsInMaze() -> Int
  func character(atRow row: Int, column: Int) -> Character?
}
```

Next, we'll create a class called MazeData that will be responsible for storing the information about the maze and acting as the delegate for the MazeViewController. The MazeData class will need to implement the MazeDataProvider protocol and provide an implementation for the required methods. It might look something like this:

```swift
class MazeData: MazeDataProvider {
  private var maze: [[Character]] = [
    ["#", "#", "#", "#", "#"],
    ["#", " ", " ", " ", "#"],
    ["#", " ", "#", " ", "#"],
    ["#", " ", " ", " ", "#"],
    ["#", "#", "#", "#", "#"]
  ]

  func numberOfRowsInMaze() -> Int {
    return maze.count
  }

  func numberOfColumnsInMaze() -> Int {
    return maze[0].count
  }

  func character(atRow row: Int, column: Int) -> Character? {
    guard row >= 0 && row < numberOfRowsInMaze() && column >= 0 && column < numberOfColumnsInMaze() else {
      return nil
    }
    return maze[row][column]
  }
}
```

Finally, we'll update the MazeViewController to use an instance of MazeData as its delegate. We'll also update the MazeViewController to use the delegate to get the information it needs to display the maze on the screen. The MazeViewController might look something like this:

```swift
class MazeViewController: UIViewController {
  var dataProvider: MazeDataProvider?

  override func viewDid
```

