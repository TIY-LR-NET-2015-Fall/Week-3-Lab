# Week-3-Lab
Messaging API

## Description
Web API Project that allows users to create and see messages.


## Objectives

### Learning Objectives

After completing this assignment, you should…

* Understand ReST
* Create an API that others can use
* Use Memory Caching


### Performance Objectives

After completing this assignment, you be able to effectively use

* Web API Routing
* Calling API's


## Details

Code you may want
-----------------

```c#
  private List<Post> GetPosts()
        {
            //Retrieve out of the cache the current posts.
            MemoryCache memoryCache = MemoryCache.Default;
            var posts = (List<Post>)memoryCache.Get("BLAH");

            if (posts == null)
            {
                posts = new List<Post>();
                memoryCache.Set("BLAH", posts, DateTimeOffset.Now.AddSeconds(10));
            }

            return posts;
        }
        private void SavePosts(List<Post> posts)
        {
            //put the list of posts back in to the cache.
            MemoryCache memoryCache = MemoryCache.Default;
            memoryCache.Set("BLAH", posts, DateTimeOffset.Now.AddSeconds(10));

        }
```

### Deliverables

* A pull request containing your projects and code


### Requirements

## Normal Mode

0. Have a Web API application that a user can ask for all messages and add messages
1. Have a Console App that uses Rest Sharp that calls your API
2. Your console application asks for input from the user and then posts it as a message to the api.


## Hard Mode

0. ALlow users to delete messages that only they made.


## Nightmare Mode

0. Allow users to post to different channels.
