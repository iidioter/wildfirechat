# 用户

#### 用户的基本属性
用户拥有如下三个属性，userId、name、displayName。
 * userId 用户在系统中的唯一ID，一般是一个字符串，具有系统中唯一性，用户在使用过程中无法看到，不可以修改。野火IM中用户ID最大长度是64字节。
 * name 有人也称为loginName或accountName，一般是用来登陆时填写的用户名，具有系统中的唯一性，一般不可以修改。野火IM中name最大长度也是64字节
 * displayName 有人也称为nickName，一般情况下用户可以随意修改，不要求唯一性。displayName最大长度也是64字节。
 > 其它的一些属性，比如头像，号码，地址等，不容易引起误解这里就不做解释了。另外用户提供有extra字段，客户可以自定义使用。

#### 登陆与连接
登陆与连接是两个不同的概念。登陆是指应用认证用户的一个过程，登陆成功后，应用可以识别当前用户，并授权用户对应的权限。连接这里指的是IM的长链接建立，是发生在登陆之后，需要保持与IM服务器长链接，以便发送消息或者接收消息推送。

#### 用户Token
用户Token，在不引起歧义的情况下称为token。token是用户身份验证的凭证，在IM连接之前，需要先换取token，一般是在登陆成功时，由应用服务器返回token，使用token连接IM服务器，IM服务器会对token的有效性进行检查。token作为客户的连接凭证，需要严格保密。

#### 连接
SDK仅需要用户ID和token进行连接，在IM系统核心处理部分，只用到用户ID，不需要系统中一定有这个用户，这样客户就可以选择是否托管用户信息。