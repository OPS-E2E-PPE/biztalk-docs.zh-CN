---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e32af9507ff3e7079bb6d1110f93439c90a19852
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393258"
---
# <a name="setting-peoplesoft-transport-properties"></a>设置 PeopleSoft 传输属性
PeopleSoft 传输属性用于设计和运行时。 在中**传输属性**对话框中，您设置的连接和凭据参数特定于服务器系统和你尝试访问的对象。  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
### <a name="to-create-a-send-port"></a>若要创建的发送端口  
  
1.  展开适配器必需属性，填写连接到 PeopleSoft 服务器的所有所需信息。  
  
     必须设置连接到 PeopleSoft Enterprise 的 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器的配置参数。 此数据是区分大小写。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Application Server Path`|表示的计算机和 PeopleSoft 应用程序服务器是运行和侦听的端口的字符串。 PeopleSoft 8 应用程序的 URL 路径的语法是 / / < 计算机名 >:\<端口\>。 询问有关 PeopleSoft 管理员\<端口\>值。 \<端口\>值指的是 JOLT 协议侦听程序端口，不是应用程序服务器端口。 默认 JOLT 端口为 9000。|  
    |`JAVA_HOME`|设置 JAVA_HOME 变量以指向您的 JDK 安装，例如：**C:\j2sdk1.4.2_08**.|  
    |`Password`|如果未选中**使用 SSO**，必须设置凭据参数以便用于访问服务器系统的 PeopleSoft Enterprise 的 BizTalk 适配器。<br /><br /> 表示用户的密码登录到 PeopleSoft 系统的字符串。 字符不会出现，但由星号 （*） 表示。|  
    |`PeopleSoft 8.x Jar Files`|若要使用组件接口 (仅适用于 PeopleSoft 8)，则必须更新 CLASSPATH 以包含 PeopleSoft 组件接口 jar 文件。 例如： **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**。|  
    |`User Name`|如果未选中**使用 SSO**，必须设置凭据参数以便用于访问服务器系统的 PeopleSoft Enterprise 的 BizTalk 适配器。<br /><br /> 表示用于登录到 PeopleSoft 系统的用户名称的字符串。|  
  
2.  输入**其他参数**时日期用作键的值; 它具有不同的格式。 年-月-日是默认格式。  
  
3.  输入**并发控制**值，该值表示在调用，例如 200 数**最大并发调用**如有必要。  
  
     **最大并发调用**参数激活过载保护，如果后端服务器无法处理的数据量。 并行调用是为其适配器还没有回复的请求。 设置**最大并发调用**中在吞吐量超过了后端处理能力。  
  
     默认值为此字段为-1，这意味着无保护时发生。  
  
     如果 BizTalk Server 将提交到传输适配器的请求和调用等于或超过设置的值的并发数**最大并发调用**、 提交直到并发调用数，已保存请求的线程为降低到低于设置的值。  
  
## <a name="see-also"></a>请参阅  
 [创建 PeopleSoft 发送处理程序](../core/creating-peoplesoft-send-handlers.md)