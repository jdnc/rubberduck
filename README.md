# About rubberduck
rubberduck is based on the idea of [Rubberduck debugging] (https://en.wikipedia.org/wiki/Rubber_duck_debugging). Debugging large code bases can quickly become frustrating. It really helps to clear your thoughts by talking through and explaining your code to someone.
rubberduck is your friendly bot that will help you reason about your code from scratch. Hopefully at the end of a conversation, you will have your bug all figured out!

Here's a sample session with rubberduck:

  rubberduck: First of all close your eyes and take 3 huge, deep breaths. Trust me this is the most important step!
  rubberduck: Done, all right tell me what exactly is the bug that you are seeing?
  you: I see that all the epoll instances are not getting notified of events.
  rubberduck: I see, how do epoll instances get notified?
  you: Well the main thread writes events to the write pipe and the epoll instances monitor the read end of the pipes
  rubberduck: So then, what are the possible reasons that epoll is not being notified? Give me reasons 1 by 1
  rubberduck: reason 1?
  you: the main thread isn't writing some events
  rubberduck: all right did you confirm if this is the reason?
  you: yes I checked, that part is fine
  rubberduck: what could another reason be?
  you: the read pipes are somehow not getting the reads, maybe there is something wrong with the pipe?
  rubberduck: Yes, that might be. I think you should verify if this is what is happening.
  you: I checked, the read pipes are working fine as well, there are events there as well, but the notifications aren't happening
  rubberduck: I see, is there any other reason that you can think of?
  you: well maybe epoll notifications are not working as expected?
  rubberduck: Why would the epoll notifications not work as expected?
