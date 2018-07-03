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
# <a name="deployment-limitations"></a><span data-ttu-id="55e0b-101">部署限制</span><span class="sxs-lookup"><span data-stu-id="55e0b-101">Deployment Limitations</span></span>
<span data-ttu-id="55e0b-102">传输适配器密码存储为星号 (\*\*\*\*\*\*) 中的绑定文件导出的 BizTalk 部署向导，并传递到管理相同的格式中的组件。</span><span class="sxs-lookup"><span data-stu-id="55e0b-102">The Transport Adapter password is stored as asterisks (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Deployment Wizard, and is passed to the management component in the same format.</span></span> <span data-ttu-id="55e0b-103">在导入之前编辑绑定文件，将星号替换为随机的字母数字值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="55e0b-103">Edit the binding file before importing by replacing the asterisks with random alphanumeric values (that is, not the correct password).</span></span> <span data-ttu-id="55e0b-104">然后输入正确的密码使用**传输属性**导入绑定文件后的页。</span><span class="sxs-lookup"><span data-stu-id="55e0b-104">Then enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
 <span data-ttu-id="55e0b-105">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="55e0b-105">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="55e0b-106">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="55e0b-106">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="55e0b-107">下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="55e0b-107">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="55e0b-108">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="55e0b-108">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="55e0b-109">在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。</span><span class="sxs-lookup"><span data-stu-id="55e0b-109">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  

## <a name="password-limitation-workaround"></a><span data-ttu-id="55e0b-110">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="55e0b-110">Password Limitation Workaround</span></span>  
 <span data-ttu-id="55e0b-111">使用以下方法之一作为密码限制的解决方法。</span><span class="sxs-lookup"><span data-stu-id="55e0b-111">Use one of the following as a work-around for the password limitation.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="55e0b-112">若要解决密码限制</span><span class="sxs-lookup"><span data-stu-id="55e0b-112">To work around the password limitation</span></span>  
  
1. <span data-ttu-id="55e0b-113">在导入之前编辑绑定文件，将星号替换为明文密码。</span><span class="sxs-lookup"><span data-stu-id="55e0b-113">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="55e0b-114">出于安全原因，这不被建议。</span><span class="sxs-lookup"><span data-stu-id="55e0b-114">This is not recommended for security reasons.</span></span>  
  
2. <span data-ttu-id="55e0b-115">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="55e0b-115">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="55e0b-116">输入正确的密码使用**传输属性**导入绑定文件后的页。</span><span class="sxs-lookup"><span data-stu-id="55e0b-116">Enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="55e0b-117">只有当目标计算机上安装了 Microsoft Visual Studio 或者开发一个自定义工具，才能使用这种解决方法。</span><span class="sxs-lookup"><span data-stu-id="55e0b-117">This work-around can be used only if Microsoft Visual Studio is installed on the target computer or by developing a custom tool.</span></span>  
  
   <span data-ttu-id="55e0b-118">**- 或 -**</span><span class="sxs-lookup"><span data-stu-id="55e0b-118">**-OR-**</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="55e0b-119">若要解决密码限制</span><span class="sxs-lookup"><span data-stu-id="55e0b-119">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="55e0b-120">使用企业单一登录，而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="55e0b-120">Use Enterprise Single Sign-On instead of using passwords.</span></span>  
  
     <span data-ttu-id="55e0b-121">使用 SSO 选项需要任何额外操作;仅导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="55e0b-121">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="55e0b-122">验证逻辑系统以及传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="55e0b-122">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e0b-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="55e0b-123">See Also</span></span>  
 <span data-ttu-id="55e0b-124">[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="55e0b-124">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="55e0b-125">导入 JD Edwards OneWorld 应用程序</span><span class="sxs-lookup"><span data-stu-id="55e0b-125">Import the JD Edwards OneWorld app</span></span>](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)