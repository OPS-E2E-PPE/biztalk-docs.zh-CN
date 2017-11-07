---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: acc8560096423eb69b7cad8d9e6264707ae9a636
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="deployment-limitations"></a>部署限制

## <a name="overview"></a>概述
传输适配器密码在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导出的绑定文件中以星号 (******) 的形式进行存储，并且以同样的格式传递至管理组件。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，必须在完成导入操作后从绑定文件中删除密码。  
  

## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 若要解决此密码限制问题，可使用以下方法之一：  
  
-   在导入之前编辑绑定文件，将星号替换为明文密码。  
  
    > [!CAUTION]
    >  出于安全考虑，不建议使用此方法。  
  
-   在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用**传输属性**在 BizTalk Server 管理控制台中导入的绑定文件后的页。  
  
    > [!NOTE]
    >  只有当目标计算机上安装了 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 或者您开发了一个自定义工具时，才能使用这种解决方法。  
  
 - 或 -  
  
-   使用企业单一登录 (SSO) 而不是使用密码。  
  
     使用 SSO 选项时需要导入绑定文件。  
  
 验证逻辑系统以及传输和接收服务。  
  
## <a name="see-also"></a>另请参阅  
[导入绑定和限制](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)