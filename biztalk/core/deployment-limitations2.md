---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 8a61c55439b5e5f8455b21e59fae06c559b5ff16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389517"
---
# <a name="deployment-limitations"></a>部署限制
传输适配器密码存储为星号 (\*\*\*\*\*\*) 中的绑定文件导出的 BizTalk 部署向导，并传递到管理相同的格式中的组件。 将星号替换随机字母数字值 （即，不正确的密码） 导入之前编辑绑定文件。 然后输入正确的密码使用**传输属性**导入绑定文件后的页。  
  
 在导出绑定信息时，得到的绑定文件不包含任何传输所使用的密码中的适配器接收位置/发送端口。 这可以防止以明文形式显示密码信息。 下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。 或者，暂时可以通过将密码输入到其导入前修改绑定文件。 在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。  
  

## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 使用以下项之一以解决密码限制。  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决密码限制  
  
1. 星号替换为纯文本导入之前编辑绑定文件。  
  
   > [!CAUTION]
   >  出于安全原因，这不被建议。  
  
2. 星号替换为某些无效的值 （即，不正确的密码） 导入之前编辑绑定文件。 输入正确的密码使用**传输属性**导入绑定文件后的页。  
  
   > [!NOTE]
   >  这种解决可仅当目标计算机上或通过开发一个自定义工具来安装 Microsoft Visual Studio。  
  
   **- 或 -**  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决密码限制  
  
1.  使用企业单一登录，而不是使用密码。  
  
     使用 SSO 选项需要任何额外操作;仅导入绑定文件。  
  
2.  验证逻辑系统以及传输和接收服务。  
  
## <a name="see-also"></a>请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [导入 JD Edwards OneWorld 应用程序](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)