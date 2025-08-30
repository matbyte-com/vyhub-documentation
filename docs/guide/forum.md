# Forum

The VyHub forum is perfectly integrated in the VyHub system. Players can just keep using their accounts without a need
to newly register.

> The Forum is a premium add-on and costs monthly. After you purchased the addon in
> [VyHub Central](https://app.vyhub.net/dashboard), it must be activated in the general settings of your instance.

## Features
- Unlimited Topic Categories, Topics, Threads, and Posts
- Forum statistics (Thread- and post count)
- Last posts and last threads
- Simple and easy-to-use design
- Perfect integration into VyHub
- Advanced rights features
- Reactions with Emojis

## Objects

### Topic Category

| Attribute                             | Description                                                          |
|---------------------------------------|----------------------------------------------------------------------|
| Title                                 | Title of topic category                                              |
| [Requirement Set](requirement_set.md) | Can be used to control the access of the users to the topic category |

### Topic

| Attribute              | Description                                                                                                                              |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Title                  | Title of topic                                                                                                                           |
| Description            | [Optional] Description of topic                                                                                                          |
| Icon                   | [Optional] Icon for topic                                                                                                                |
| Topic Category         | The topics topic category. The topic is organised under the topic                                                                        | 
| Edit post              | Whether users can edit their own posts. Users with the property `forum_edit` and topic admins can edit at any time                       |
| Prohibit create thread | Prohibits users from creating threads in this topic. Users with the property `forum_edit` and topic admins can create posts at any time. |
| Admins                 | [Optional] List of users, which can edit and delete threads and posts.                                                                   |

### Thread

| Attribute | Description                        |
|-----------|------------------------------------|
| Title     | Title of thread                    |
| Status    | Used to close and archive a thread |

### Post

| Attribute | Description     |
|-----------|-----------------|
| Content   | Content of post |

## Access Control

- Admins and users with the `forum_edit` property can edit everything and can create topic categories and topics.
- Topic admins can be set in the topic settings. They can edit and delete every thread and every post of users. You can consider them as moderators.
- The edit_post setting in the topic is used to allow users to edit their own posts. Otherwise, users cannot edit their posts.
- Team-only parts of the forum are possible with [requirement sets](requirement_set.md). 

## FAQ

| Frequently Asked Questions                                                                                                                                                                                | 
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| __Question:__ I have bought the forum addon. Why can't I find it? <br>  __Solution:__ You need to also activate the Forum in the general settings of your instance.                                       |
| __Question:__ Users can't edit their posts, how do I change that? <br> __Solution:__ You can find the `edit_post` setting in the settings of the respective topic.                                        |
| __Question:__ I want to create a team only forum. Is that possible? <br> __Solution:__ Yes, that is possible with requirement sets. Find examples in the [requirement](requirement_set.md) documentation. |
