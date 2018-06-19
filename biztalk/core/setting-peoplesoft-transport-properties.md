---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 1772a30ce5496a3a14866da168a56958bc3bc78c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974091"
---
# <a name="setting-peoplesoft-transport-properties"></a>设置 PeopleSoft 传输属性
PeopleSoft 传输属性用于运行时和设计时。 在**传输属性**对话框中，你设置的连接和凭据参数特定于服务器系统和你尝试访问的对象。  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
### <a name="to-create-a-send-port"></a>创建发送端口的步骤  
  
1.  展开“适配器必需属性”，然后填写连接到 PeopleSoft 服务器所需的各项信息。  
  
     必须设置配置参数才能将适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器连接到 PeopleSoft Enterprise。 此数据是区分大小写。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Application Server Path`|此字符串代表 PeopleSoft 应用程序服务器运行的计算机和侦听的端口。 PeopleSoft 8 应用程序的 URL 路径的语法是 / / < 计算机名 >:\<端口\>。 向你 PeopleSoft 管理员请求\<端口\>值。 \<端口\>值是震动协议侦听器端口，不是应用程序服务器端口。 默认 JOLT 端口为 9000。|  
    |`JAVA_HOME`|设置 JAVA_HOME 变量以指向你 JDK 的安装，例如： **C:\j2sdk1.4.2_08**。|  
    |`Password`|如果你未选择**使用 SSO**，必须设置为 BizTalk 适配器 PeopleSoft 企业访问服务器系统的凭据参数。<br /><br /> 表示用户密码的字符串，用于登录到 PeopleSoft 系统。 不会显示密码中的字符，而是以星号 (*) 表示这些字符。|  
    |`PeopleSoft 8.x Jar Files`|若要使用组件接口（仅限 PeopleSoft 8），则必须更新 CLASSPATH 以包含 PeopleSoft 组件接口 jar 文件。 例如： **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**。|  
    |`User Name`|如果你未选择**使用 SSO**，必须设置为 BizTalk 适配器 PeopleSoft 企业访问服务器系统的凭据参数。<br /><br /> 表示用户名的字符串，用于登录到 PeopleSoft 系统。|  
  
2.  输入**其他参数**时日期用作键的值; 它具有不同的格式。 YYYY-月-日是默认格式。  
  
3.  输入**并发控制**值在表示的调用，例如 200、 数**最大并发调用**如有必要。  
  
     **最大并发调用**参数激活过载保护，如果后端服务器无法处理的数据量。 并行调用是适配器尚未进行回复的请求。 设置**最大并发调用**其中吞吐量超过后端处理功能的实例中。  
  
     此字段的默认值为 -1，意味着未进行任何保护。  
  
     如果 BizTalk Server 将请求提交到传输适配器，并且调用等于或超过为设置的值的并发数**最大并发调用**，提交请求被保存，直到并发调用数量的线程为降低到低于设置的值。  
  
## <a name="see-also"></a>另请参阅  
 [创建 PeopleSoft 发送处理程序](../core/creating-peoplesoft-send-handlers.md)