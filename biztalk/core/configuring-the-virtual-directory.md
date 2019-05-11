---
title: 配置虚拟目录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
ms.assetid: 548e3bee-66bc-424c-895d-e8672a3d6301
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05f694744076f4242309ed58a70903fb7aaedbda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355150"
---
# <a name="configuring-the-virtual-directory"></a><span data-ttu-id="2e7b9-102">配置虚拟目录</span><span class="sxs-lookup"><span data-stu-id="2e7b9-102">Configuring the Virtual Directory</span></span>
<span data-ttu-id="2e7b9-103">本主题介绍配置虚拟目录和验证用户的应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-103">This topic shows the procedures for configuring the virtual directory and verifying the application for a user.</span></span>  
  
## <a name="configuring-the-directory"></a><span data-ttu-id="2e7b9-104">配置目录</span><span class="sxs-lookup"><span data-stu-id="2e7b9-104">Configuring the Directory</span></span>  
  
#### <a name="to-configure-the-virtual-directory"></a><span data-ttu-id="2e7b9-105">若要配置的虚拟目录</span><span class="sxs-lookup"><span data-stu-id="2e7b9-105">To configure the virtual directory</span></span>  
  
1.  <span data-ttu-id="2e7b9-106">%Systemdrive%上创建一个文件夹以将配置为虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-106">On the %systemdrive%, create a folder to be configured as a virtual directory.</span></span>  
  
2.  <span data-ttu-id="2e7b9-107">单击**启动**，依次指向**程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-107">Click **Start**, point to **Programs**, click **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
3.  <span data-ttu-id="2e7b9-108">展开**\<服务器名称\>** ，然后展开**站点**。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-108">Expand **\<server name\>** and then expand **Sites**.</span></span>  
  
4.  <span data-ttu-id="2e7b9-109">右键单击**Default Web Site**然后单击**添加虚拟目录**。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-109">Right-click **Default Web Site** and click **Add Virtual Directory**.</span></span>  
  
5.  <span data-ttu-id="2e7b9-110">在中**添加虚拟目录**对话框框中，键入别名。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-110">In the **Add Virtual Directory** dialog box, type the alias.</span></span>  
  
6.  <span data-ttu-id="2e7b9-111">键入在步骤 1 中创建的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-111">Type the path of the folder created in step 1.</span></span> <span data-ttu-id="2e7b9-112">此外，也可以单击 **（...）** 以浏览到文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-112">Alternatively, click **(…)** to browse to the folder location.</span></span>  
  
7.  <span data-ttu-id="2e7b9-113">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-113">Click **OK**.</span></span> <span data-ttu-id="2e7b9-114">该文件夹将显示下**Default Web Site**文件夹。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-114">The folder is displayed under the **Default Web Site** folder.</span></span>  
  
8.  <span data-ttu-id="2e7b9-115">右键单击该文件夹，然后单击**转换为应用程序**。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-115">Right-click the folder and click **Convert to Application**.</span></span>  
  
9. <span data-ttu-id="2e7b9-116">在中**添加应用程序**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-116">In the **Add Application** dialog box, click **OK**.</span></span> <span data-ttu-id="2e7b9-117">该文件夹转换为应用程序 （您可以看到图标 – 从文件夹图标变为网站图标中的更改）。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-117">The folder is converted to an application (you can see the change in the icon – from a folder icon to the Web site icon).</span></span>  
  
## <a name="verifying-an-application-for-a-user"></a><span data-ttu-id="2e7b9-118">验证应用程序的用户</span><span class="sxs-lookup"><span data-stu-id="2e7b9-118">Verifying an Application for a User</span></span>  
 <span data-ttu-id="2e7b9-119">Internet 信息服务 (IIS) 应用程序运行在高度隔离;因此，必须验证该应用程序可以运行的 BizTalk Server Isolated Host Users 组中的用户上下文中使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-119">Internet Information Services (IIS) applications run in high isolation; therefore, you must verify that the application can run in the context of a user in the BizTalk Server Isolated Host Users group by using the following procedure.</span></span>  
  
#### <a name="to-verify-an-application-for-a-user"></a><span data-ttu-id="2e7b9-120">若要验证用户的应用程序</span><span class="sxs-lookup"><span data-stu-id="2e7b9-120">To verify an application for a user</span></span>  
  
1.  <span data-ttu-id="2e7b9-121">在控制面板中，打开**管理工具**，然后单击**组件服务**。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-121">In Control Panel, open **Administrative Tools**, and then click **Component Services**.</span></span>  
  
2.  <span data-ttu-id="2e7b9-122">导航到中的 COM + 应用程序**组件服务**。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-122">Navigate to the COM+ application in **Component Services**.</span></span>  
  
3.  <span data-ttu-id="2e7b9-123">右键单击 COM + 应用程序，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-123">Right-click the COM+ application, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2e7b9-124">单击**标识**和更改此 COM + 应用程序运行是 BizTalk Server 组的成员的用户的标识。</span><span class="sxs-lookup"><span data-stu-id="2e7b9-124">Click **Identify** and change the identity under which this COM+ application runs to a user that is a member of a BizTalk Server group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7b9-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e7b9-125">See Also</span></span>  
 [<span data-ttu-id="2e7b9-126">适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="2e7b9-126">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)