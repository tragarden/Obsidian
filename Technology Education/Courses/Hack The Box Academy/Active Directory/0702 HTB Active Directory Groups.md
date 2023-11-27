# Active Directory Groups

### Groups

Groups are an #object of great interest to attackers as group access grants rights that can lead to privilege escalation. It is important to regularly audit your groups and pare down any excessive assignments of rights, or making sure that users are not assigned to groups that are outside of the scope of their daily work.

### Organizational Units

Organizational Units ( #OU) are often confused with groups, and a simple way of thinking can help you understand the difference. On the most fundamental level, Groups are used to assign rights to a set of users, while Operational Units are used to group higher level objects like groups, users, and devices.

Groups are useful for assigning rights to many users at once using the parent-child inheritance of the group policies. Groups have both a type and a scope.

### Group Type and Scope

#### Group Type

Group Type indicates the purpose of the group and must be selected when creating the group. There are two types of group: security and distribution.

Security groups are used by administrators to assign permissions and manage rights.

Distribution groups do not assign permissions, instead they are used to distribute messages to users in the group. This works similar to a mailing list associated with emails. 

#### Group Scope

Group Scope illustrates how the group operates within a given domain. There are three types of scope.

Domain Local Group operate locally within the domain that they were created within. While these local groups cannot be used in other domains, other users are able to access this local domain. You can nest these local groups within each other, but you cannot move these local groups outside into the global groups. 

Global Groups yield access to other domains and can only include accounts from the same domain from which it was created. Global groups can be added to both global and local groups.

Universal Groups are all encompassing groups stored in the Global Catalog ( #GC) that can manage any #object within the entire #forest. Changes to this group will cause replication to occur across every domain within the forest.

Built-In groups are created for administrative purposes when a domain is created. Domain Admins is an example of a built-in group that is a global security group.

Custom groups are created by the administrator to manage organization specific roles and messages.

Nested Group Membership is core concept for Group Management and an administrator must have a firm understanding of how these hierarchies work so that they do not create vulnerabilities that enable privilege escalation. An admin can use a tool like #Bloodhound to find flaws in their group permission logic. 

### Notable Attributes

Common Name, or 'cn', is the name of the group.

'member' indicates the users, groups, and contacts within the given group.

'groupType' is an integer that indicates the type and scope of the group.

'memberOf' indicates any groups that have a nested group membership.

'objectSid' displays the SID of the group which identifies the group as a  security principal.