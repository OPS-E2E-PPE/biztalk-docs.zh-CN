---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 39b22cf6bf77f6e23b4a242e8c711070ef8a153c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530845"
---
# <a name="deployment-limitations"></a>部署限制
传输适配器密码在导出的绑定文件中存储为星号 （*） [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将其传递到相同的格式中的管理组件。 星号替换为某些无效的值 （即，不正确的密码） 导入之前编辑绑定文件。  
  
 在导出绑定信息时，得到的绑定文件不包含任何传输所使用的密码中的适配器接收位置/发送端口。 这可以防止以明文形式显示密码信息。 下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。  
  
 或者，暂时可以通过将密码输入到其导入前修改绑定文件。 在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。  
  
## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 若要解决密码限制，你可以执行以下操作。  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决密码限制  
  
1.  使用企业单一登录，而不是使用密码。 使用 SSO 选项需要任何额外操作;仅导入绑定文件。  
  
2.  验证逻辑系统以及传输和接收服务。  
  
## <a name="see-also"></a>请参阅  
 [导入 JD Edwards EnterpriseOne 应用程序](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)