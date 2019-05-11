---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 9fa12a82defc21cf0094cad7164ddd096442d87e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351839"
---
# <a name="deployment-limitations"></a>部署限制

## <a name="overview"></a>概述
传输适配器密码在导出的绑定文件中存储为星号 （*） [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将其传递到相同的格式中的管理组件。  
  
 在导出绑定信息时，得到的绑定文件不包含任何传输所使用的密码中的适配器接收位置/发送端口。 这可以防止以明文形式显示密码信息。 下一次使用该文件导入绑定信息时，您必须使用传输属性页用户界面中输入的密码。 或者，暂时可以通过将密码输入到其导入前修改绑定文件。 在这种情况下，必须从绑定文件删除密码，在导入操作完成后。  
  

## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 若要解决此密码限制，可以使用以下方法之一：  
  
- 星号替换为纯文本导入之前编辑绑定文件。  
  
  > [!CAUTION]
  >  出于安全原因不推荐此操作。  
  
- 星号替换为某些无效的值 （即，不正确的密码） 导入之前编辑绑定文件。 输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。  
  
  > [!NOTE]
  >  这种解决可以仅当使用 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]安装在目标计算机上或者您开发一个自定义工具。  
  
  -或-  
  
- 使用企业单一登录 (SSO) 而不是使用密码。  
  
   使用 SSO 选项，需要导入绑定文件。  
  
  验证逻辑系统以及传输和接收服务。  
  
## <a name="see-also"></a>请参阅  
[导入绑定和限制](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)