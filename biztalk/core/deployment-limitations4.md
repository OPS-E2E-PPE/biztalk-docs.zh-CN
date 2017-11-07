---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 847e66c189cb8fc14014691f95d78b6eec4b45dc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="f66ac-101">部署限制</span><span class="sxs-lookup"><span data-stu-id="f66ac-101">Deployment Limitations</span></span>
<span data-ttu-id="f66ac-102">传输适配器密码为星号 （*） 存储在由导出绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将它传递给相同的格式中的管理组件。</span><span class="sxs-lookup"><span data-stu-id="f66ac-102">The Transport Adapter password is stored as stars (******) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="f66ac-103">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="f66ac-103">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="f66ac-104">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="f66ac-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="f66ac-105">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="f66ac-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="f66ac-106">下次使用文件导入绑定信息，你必须通过使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="f66ac-106">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="f66ac-107">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="f66ac-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="f66ac-108">在这种情况下，必须从绑定文件删除密码，导入操作成功完成后。</span><span class="sxs-lookup"><span data-stu-id="f66ac-108">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="f66ac-109">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="f66ac-109">Password Limitation Workaround</span></span>  
 <span data-ttu-id="f66ac-110">若要解决此密码限制问题，您可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="f66ac-110">To work around the password limitation, you can do the following.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="f66ac-111">若要解决的密码限制</span><span class="sxs-lookup"><span data-stu-id="f66ac-111">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="f66ac-112">使用企业单一登录，而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="f66ac-112">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="f66ac-113">使用的 SSO 选项需要在没有额外的工作;仅导入的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="f66ac-113">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="f66ac-114">验证逻辑的系统和传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="f66ac-114">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f66ac-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f66ac-115">See Also</span></span>  
 [<span data-ttu-id="f66ac-116">导入博士 Edwards EnterpriseOne 应用</span><span class="sxs-lookup"><span data-stu-id="f66ac-116">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)