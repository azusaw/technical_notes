Unit 4

# Access Control
## AAA Framework
The AAA framework requires an access control system to include mechanisms for:
* Authentication 
* Authorisation
* Accountability

#### Authentication
* process of verifying attributes claimed by an entity/actor
* Authentication is managed centrally, i.e. not at each server running each service.
* 1. The setting (and changing) of access controls
  * e.g. setting permissions to perform access operations 
* 2. The use by the guard of the access control information
  * e.g. consulting some data structure recording permissions
* SSO
  * Increasingly in the enterprise, users have a single set of credentials (password, smartcard, biometric) etc. 
* Identity federation
  * 企業や組織、サードパーティなど各ドメイン間での信頼関係を確立することでドメイン間でIDを共有してユーザの認証を行うこと


#### Authorisation
* deciding whether (and how) to grant access.
* How guard works
* No low-level implementation details
* Policies are also managed centrally

#### Accountability
普通は「説明責任」と訳されるが、情報セキュリティ業界では、「責任追跡性」と訳されている。
企業環境内のすべての活動をそれらの活動の源までさかのぼって追跡できるようにすること。
Accountability is linked to non-repudiation: it is not possible (or difficult) for agents to deny (repudiate)  their actions. 

## Identity and Access Management(IAM)
For enterprise

* Entity
  * could be real (e.g. a person) or virtual (e.g. a department).
  * An entity could have more than one identity,
  * every identity is associated with just one entity.

* Identity
  * Identities are entity names, including user names (from some namespace of possible names)
  * An identity can have many attributes
  * Many identities can have the same attribute (e.g. department, role, clearance level, ownership of resource)

![image](https://user-images.githubusercontent.com/72424558/205503629-831abd99-1dfc-4219-9a58-5e681fe2c8c2.png)
Entities > Identities > Identifilers

* Subject 
  * user ID
  * process, threads, services
* Object: the entity being accessed.
 
* Principal
  * Special kind of subject
  * e.g. A process (subject) may attempt to access a file (object) on behalf of a UserID
 
* Reference monitor
  * Guard
  * Who control policy

* Policy
  * The collection of all automated access rights in the system. 
  * the reference monitor just implements the technical policy. 

## Multi-user access policy
#### Discretionary Access Control (DAC)
* Define an owner for each resource
* Let the owner decide who should be allowed access. Control is at the discretion of the owner. 
* need to be able to identify other individuals.
* Often only allow individual who need-to-know.
* Github、OneNote、ほとんどのシステムがこれじゃないかな

#### Mandatory Access Control (MAC)
* Have a system-wide policy about who has access. S
* Set centrally by an administrator:
* Sometimes called rule-based access control. 
* 軍隊とかで使われる(軍曹以上のみ閲覧可能情報とか？)

## Time-of-check to time-of-use(TOCTTOU)
ソフトウェア開発において、ある条件をチェック したあと、その結果を行使 するまでに変更が発生することで引き起こされるバグの一種。
競合状態の一種。

## Access Control Matrix
#### Capabilities
* For every subject, s, keep a list of its access rights (what it can do to what). 
* Basically, the row s of the matrix.
* Difficult to know who has access to a particular object.
* Difficult to revoke permissions.

#### Access Control Lists (ACLs)
* For every object, o, keep a list of the access rights to it (who can do what to it).
* Basically, the column o of the matrix.
* ACLs much more widely used especially at OS-level
* オブジェクト視点で誰がアクセスできるか
* Difficult to find all the permissions of a particular user
* Difficult to revoke their permissions

#### Identity-based Access Control
* ACLとか、個人に対してもアクセス認可

#### Attribute-based Access Control 属性ベースのアクセスコントロール
*　XACMLという特殊な言語でポリシーを記述する
*　Groups、RBAC(Role-based access control)はこっちにみなされる
*　e.g. 
  * ドキュメントがユーザーと同じ部門にある場合、ユーザーはドキュメントを表示できます。
  * ユーザーが所有者であり、ドキュメントが下書きモードの場合、ユーザーはドキュメントを編集できます。
  * 午前 9 時より前にアクセスを拒否します。

## Memo
Onion Model of Computer Protection Mechanisms
![image](https://user-images.githubusercontent.com/72424558/205502001-4c9d9701-d6d8-4ceb-9615-486933c3eac3.png)

