---
title: 如何配置虚拟目录 |Microsoft Docs
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
- applications, verifying for users
- verifying applications for users
ms.assetid: 3da16524-8238-426a-88f8-434be5992e13
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d4a0e35a4d88c9f8a64074cef40a9c701e5e7d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385979"
---
# <a name="how-to-configure-the-virtual-directory"></a><span data-ttu-id="8cd4a-102">如何配置虚拟目录</span><span class="sxs-lookup"><span data-stu-id="8cd4a-102">How to Configure the Virtual Directory</span></span>
<span data-ttu-id="8cd4a-103">本主题介绍配置虚拟目录和验证用户的应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-103">This topic describes the procedures for configuring the virtual directory and verifying the application for a user.</span></span>  
  
### <a name="to-configure-the-virtual-directory"></a><span data-ttu-id="8cd4a-104">若要配置的虚拟目录</span><span class="sxs-lookup"><span data-stu-id="8cd4a-104">To configure the virtual directory</span></span>  
  
1.  <span data-ttu-id="8cd4a-105">%Systemdrive%上创建一个文件夹以将配置为虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-105">On the %systemdrive%, create a folder to be configured as a virtual directory.</span></span>  
  
2.  <span data-ttu-id="8cd4a-106">单击**启动**，依次指向**程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-106">Click **Start**, point to **Programs**, click **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
3.  <span data-ttu-id="8cd4a-107">展开 **\<服务器名称\>** ，然后展开**站点**。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-107">Expand **\<server name\>** and then expand **Sites**.</span></span>  
  
4.  <span data-ttu-id="8cd4a-108">右键单击**Default Web Site**然后单击**添加虚拟目录**。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-108">Right-click **Default Web Site** and click **Add Virtual Directory**.</span></span>  
  
5.  <span data-ttu-id="8cd4a-109">在中**添加虚拟目录**对话框框中，键入别名。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-109">In the **Add Virtual Directory** dialog box, type the alias.</span></span>  
  
6.  <span data-ttu-id="8cd4a-110">键入在步骤 1 中创建的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-110">Type the path of the folder created in step 1.</span></span> <span data-ttu-id="8cd4a-111">此外，也可以单击 **（...）** 以浏览到文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-111">Alternatively, click **(…)** to browse to the folder location.</span></span>  
  
7.  <span data-ttu-id="8cd4a-112">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-112">Click **OK**.</span></span> <span data-ttu-id="8cd4a-113">该文件夹将显示下**Default Web Site**文件夹。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-113">The folder is displayed under the **Default Web Site** folder.</span></span>  
  
8.  <span data-ttu-id="8cd4a-114">右键单击该文件夹，然后单击**转换为应用程序**。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-114">Right-click the folder and click **Convert to Application**.</span></span>  
  
9. <span data-ttu-id="8cd4a-115">在中**添加应用程序**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-115">In the **Add Application** dialog box, click **OK**.</span></span> <span data-ttu-id="8cd4a-116">该文件夹转换为应用程序 （您可以看到图标 – 从文件夹图标变为网站图标中的更改）。</span><span class="sxs-lookup"><span data-stu-id="8cd4a-116">The folder is converted to an application (you can see the change in the icon – from a folder icon to the Web site icon).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd4a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8cd4a-117">See Also</span></span>  
 [<span data-ttu-id="8cd4a-118">保护适配器</span><span class="sxs-lookup"><span data-stu-id="8cd4a-118">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)