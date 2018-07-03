---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 314bffd50e152c1e3141e4f644c60bdbe7a3824a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011030"
---
# <a name="deployment-limitations"></a>部署限制
传输适配器密码存储为星号 (\*\*\*\*\*\*) 中的绑定文件导出的 BizTalk 部署向导，并传递到管理相同的格式中的组件。 在导入之前编辑绑定文件，将星号替换为随机的字母数字值（即，不替换为正确密码）。 然后输入正确的密码使用**传输属性**导入绑定文件后的页。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。  
  

## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 使用以下方法之一作为密码限制的解决方法。  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决密码限制  
  
1. 在导入之前编辑绑定文件，将星号替换为明文密码。  
  
   > [!CAUTION]
   >  出于安全原因，这不被建议。  
  
2. 在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用**传输属性**导入绑定文件后的页。  
  
   > [!NOTE]
   >  只有当目标计算机上安装了 Microsoft Visual Studio 或者开发一个自定义工具，才能使用这种解决方法。  
  
   **- 或 -**  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决密码限制  
  
1.  使用企业单一登录，而不是使用密码。  
  
     使用 SSO 选项需要任何额外操作;仅导入绑定文件。  
  
2.  验证逻辑系统以及传输和接收服务。  
  
## <a name="see-also"></a>请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [导入 JD Edwards OneWorld 应用程序](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)