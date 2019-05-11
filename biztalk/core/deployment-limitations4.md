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
# <a name="deployment-limitations"></a><span data-ttu-id="8b9d3-101">部署限制</span><span class="sxs-lookup"><span data-stu-id="8b9d3-101">Deployment Limitations</span></span>
<span data-ttu-id="8b9d3-102">传输适配器密码在导出的绑定文件中存储为星号 （\*） [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将其传递到相同的格式中的管理组件。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-102">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="8b9d3-103">星号替换为某些无效的值 （即，不正确的密码） 导入之前编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-103">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="8b9d3-104">在导出绑定信息时，得到的绑定文件不包含任何传输所使用的密码中的适配器接收位置/发送端口。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="8b9d3-105">这可以防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="8b9d3-106">下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-106">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="8b9d3-107">或者，暂时可以通过将密码输入到其导入前修改绑定文件。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="8b9d3-108">在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-108">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="8b9d3-109">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="8b9d3-109">Password Limitation Workaround</span></span>  
 <span data-ttu-id="8b9d3-110">若要解决密码限制，你可以执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-110">To work around the password limitation, you can do the following.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="8b9d3-111">若要解决密码限制</span><span class="sxs-lookup"><span data-stu-id="8b9d3-111">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="8b9d3-112">使用企业单一登录，而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-112">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="8b9d3-113">使用 SSO 选项需要任何额外操作;仅导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-113">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="8b9d3-114">验证逻辑系统以及传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="8b9d3-114">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b9d3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b9d3-115">See Also</span></span>  
 [<span data-ttu-id="8b9d3-116">导入 JD Edwards EnterpriseOne 应用程序</span><span class="sxs-lookup"><span data-stu-id="8b9d3-116">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)