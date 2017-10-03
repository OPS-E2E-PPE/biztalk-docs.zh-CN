---
title: "部署 Limitations2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deployment, limitations
- passwords, adapter limitations
ms.assetid: 9db2ca70-5db2-4b14-a898-13049737c188
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05fa9704823bd7e9df9f0bc7d4516719a8a490e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="1342d-102">部署限制</span><span class="sxs-lookup"><span data-stu-id="1342d-102">Deployment Limitations</span></span>
<span data-ttu-id="1342d-103">传输适配器密码存储为星号 (\*\*\*\*\*\*)，由 BizTalk 部署向导，导出方法并传递到所管理绑定文件中在相同的格式中的组件。</span><span class="sxs-lookup"><span data-stu-id="1342d-103">The Transport Adapter password is stored as asterisks (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Deployment Wizard, and is passed to the management component in the same format.</span></span> <span data-ttu-id="1342d-104">在导入之前编辑绑定文件，将星号替换为随机的字母数字值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="1342d-104">Edit the binding file before importing by replacing the asterisks with random alphanumeric values (that is, not the correct password).</span></span> <span data-ttu-id="1342d-105">然后输入正确的密码使用**传输属性**后导入绑定文件页。</span><span class="sxs-lookup"><span data-stu-id="1342d-105">Then enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
 <span data-ttu-id="1342d-106">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="1342d-106">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="1342d-107">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="1342d-107">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="1342d-108">下次使用文件导入绑定信息，你必须通过使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="1342d-108">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="1342d-109">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="1342d-109">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="1342d-110">在这种情况下，必须从绑定文件删除密码，导入操作成功完成后。</span><span class="sxs-lookup"><span data-stu-id="1342d-110">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1342d-111">将 .msi 文件导入包含任何企业适配器的绑定信息的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序时，您可能会收到一条导入错误消息。</span><span class="sxs-lookup"><span data-stu-id="1342d-111">When importing an .msi file into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="1342d-112">受支持的修补程序是可从 Microsoft 处的错误的完整说明以及[http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us)。</span><span class="sxs-lookup"><span data-stu-id="1342d-112">A supported hotfix is available from Microsoft along with a full description of the error at [http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="1342d-113">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="1342d-113">Password Limitation Workaround</span></span>  
 <span data-ttu-id="1342d-114">使用以下方法之一作为密码限制的解决方法。</span><span class="sxs-lookup"><span data-stu-id="1342d-114">Use one of the following as a work-around for the password limitation.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="1342d-115">若要解决的密码限制</span><span class="sxs-lookup"><span data-stu-id="1342d-115">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="1342d-116">在导入之前编辑绑定文件，将星号替换为明文密码。</span><span class="sxs-lookup"><span data-stu-id="1342d-116">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="1342d-117">出于安全考虑，这不被建议。</span><span class="sxs-lookup"><span data-stu-id="1342d-117">This is not recommended for security reasons.</span></span>  
  
2.  <span data-ttu-id="1342d-118">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="1342d-118">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="1342d-119">输入正确的密码使用**传输属性**后导入绑定文件页。</span><span class="sxs-lookup"><span data-stu-id="1342d-119">Enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1342d-120">只有当目标计算机上安装了 Microsoft Visual Studio 或者开发一个自定义工具，才能使用这种解决方法。</span><span class="sxs-lookup"><span data-stu-id="1342d-120">This work-around can be used only if Microsoft Visual Studio is installed on the target computer or by developing a custom tool.</span></span>  
  
 <span data-ttu-id="1342d-121">**- 或 -**</span><span class="sxs-lookup"><span data-stu-id="1342d-121">**-OR-**</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="1342d-122">若要解决的密码限制</span><span class="sxs-lookup"><span data-stu-id="1342d-122">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="1342d-123">使用企业单一登录，而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="1342d-123">Use Enterprise Single Sign-On instead of using passwords.</span></span>  
  
     <span data-ttu-id="1342d-124">使用的 SSO 选项需要在没有额外的工作;仅导入的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="1342d-124">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="1342d-125">验证逻辑的系统和传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="1342d-125">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1342d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1342d-126">See Also</span></span>  
 <span data-ttu-id="1342d-127">[如何设置博士 Edwards OneWorld 传输属性](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1342d-127">[How to Set JD Edwards OneWorld Transport Properties](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span></span>  
 [<span data-ttu-id="1342d-128">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="1342d-128">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies4.md)