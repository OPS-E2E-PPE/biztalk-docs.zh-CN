---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 64f202316e59040a77cb04da99857e8539a184ac
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="deployment-limitations"></a>部署限制
传输适配器密码存储为星号 (\*\*\*\*\*\*)，由 BizTalk 部署向导，导出方法并传递到所管理绑定文件中在相同的格式中的组件。 在导入之前编辑绑定文件，将星号替换为随机的字母数字值（即，不替换为正确密码）。 然后输入正确的密码使用**传输属性**后导入绑定文件页。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下次使用文件导入绑定信息，你必须通过使用传输属性页用户界面中输入的密码。 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，必须从绑定文件删除密码，导入操作成功完成后。  
  

## <a name="password-limitation-workaround"></a>密码限制的解决方法  
 使用以下方法之一作为密码限制的解决方法。  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决的密码限制  
  
1.  在导入之前编辑绑定文件，将星号替换为明文密码。  
  
    > [!CAUTION]
    >  出于安全考虑，这不被建议。  
  
2.  在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用**传输属性**后导入绑定文件页。  
  
    > [!NOTE]
    >  只有当目标计算机上安装了 Microsoft Visual Studio 或者开发一个自定义工具，才能使用这种解决方法。  
  
 **- 或 -**  
  
#### <a name="to-work-around-the-password-limitation"></a>若要解决的密码限制  
  
1.  使用企业单一登录，而不是使用密码。  
  
     使用的 SSO 选项需要在没有额外的工作;仅导入的绑定文件。  
  
2.  验证逻辑的系统和传输和接收服务。  
  
## <a name="see-also"></a>另请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [导入博士 Edwards OneWorld 应用](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)