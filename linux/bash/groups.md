# Using the id command
The id command prints information about the specified user and its groups. If the username is omitted it shows information for the current user.

For example to get information about the user linuxize you would type:
```bash
id linuxize
```

To get a list of all groups a specific user belongs to, provide the username to the groups command as an argument:

```bash
groups linuxize
```

Just `groups` for the current user
```bash
groups
```

# List All Members of a Group
To list all members of a group, use the getent group command followed by the group name.

For example, to find out the members of a group with the name developers you would use the following command:
```bash
getent group developers
```

You can also use awk or cut to print only the first field containing the name of the group:
```bash
getent group | awk -F: '{ print $1}'
```
[link](https://linuxize.com/post/how-to-list-groups-in-linux/)
