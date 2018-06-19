---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 847e66c189cb8fc14014691f95d78b6eec4b45dc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013356"
---
# <a name="deployment-limitations"></a>部署限制
传输适配器密码为星号 （*） 存储在由导出绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将它传递给相同的格式中的管理组件。 在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下次使用文件导入绑定信息，你必须通过使用传输属性页用户界面中输入的密码。  
  
 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，必须从绑定文件删除密码，导入操作成功完成后。  
  
## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 若要解决此密码限制问题，您可以执行以下操作。  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决的密码限制  
  
1.  使用企业单一登录，而不是使用密码。 使用的 SSO 选项需要在没有额外的工作;仅导入的绑定文件。  
  
2.  验证逻辑的系统和传输和接收服务。  
  
## <a name="see-also"></a>另请参阅  
 [导入博士 Edwards EnterpriseOne 应用](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)