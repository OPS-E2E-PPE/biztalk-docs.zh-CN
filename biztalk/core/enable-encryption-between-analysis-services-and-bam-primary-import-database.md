---
title: 如何启用 Analysis Services 和 BAM 主导入数据库之间加密 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Analysis Services, enabling encryption
- Primary Import database [BAM], SQL Server Analysis Services
- Primary Import database [BAM], enabling encryption
- SQL Server Analysis Services, Primary Import database [BAM]
ms.assetid: 8107c557-e57c-4569-9ff7-abcb7a8e5243
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0de57b8faf73923a8ff5d38c17d693e45afd7b57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349911"
---
# <a name="how-to-enable-encryption-between-analysis-services-and-the-bam-primary-import-database"></a><span data-ttu-id="962b6-102">如何进行 Analysis Services 和 BAM 主导入数据库之间启用加密</span><span class="sxs-lookup"><span data-stu-id="962b6-102">How to Enable Encryption Between Analysis Services and the BAM Primary Import Database</span></span>
<span data-ttu-id="962b6-103">不启用默认情况下在安装或升级 BAM 期间进行加密。</span><span class="sxs-lookup"><span data-stu-id="962b6-103">Encryption is not enabled by default during an installation or upgrade of BAM.</span></span> <span data-ttu-id="962b6-104">若要启用加密，必须为值 1 在 BAM 配置 XML 文件中设置的 UseEncryption 标志。</span><span class="sxs-lookup"><span data-stu-id="962b6-104">To enable encryption, you must set the UseEncryption flag in the BAM configuration XML file to a value of 1.</span></span>  
  
 <span data-ttu-id="962b6-105">此外必须启用 SQL Server Analysis Services 中的加密。</span><span class="sxs-lookup"><span data-stu-id="962b6-105">You must also enable encryption in SQL Server Analysis Services.</span></span> <span data-ttu-id="962b6-106">有关启用加密的详细信息，请参阅[使用 Analysis Services 实例保护客户端通信](http://go.microsoft.com/fwlink/?LinkId=190805)(http://go.microsoft.com/fwlink/?LinkId=190805)。</span><span class="sxs-lookup"><span data-stu-id="962b6-106">For more information about enabling encryption, see [Securing Client Communication with an Analysis Services Instance](http://go.microsoft.com/fwlink/?LinkId=190805) (http://go.microsoft.com/fwlink/?LinkId=190805).</span></span>  
  
### <a name="to-enable-encryption-between-sql-server-analysis-services-and-the-bam-primary-import-database"></a><span data-ttu-id="962b6-107">若要启用 SQL Server Analysis Services 和 BAM 主导入数据库之间的加密</span><span class="sxs-lookup"><span data-stu-id="962b6-107">To enable encryption between SQL Server Analysis Services and the BAM Primary Import Database</span></span>  
  
1. <span data-ttu-id="962b6-108">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="962b6-108">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="962b6-109">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="962b6-109">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
3. <span data-ttu-id="962b6-110">类型**bm 获取配置-FileName:\<输出文件\>**。</span><span class="sxs-lookup"><span data-stu-id="962b6-110">Type **bm get-config -FileName:\<output file\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="962b6-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="962b6-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="962b6-112">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="962b6-112">Press **ENTER**.</span></span>  
  
5. <span data-ttu-id="962b6-113">打开文件配置文件已在文本编辑器中导出，并将 UseEncryption 属性标志的值更改为 1。</span><span class="sxs-lookup"><span data-stu-id="962b6-113">Open the file configuration file that you have exported in a text editor and change the value of the UseEncryption property flag to 1.</span></span>  
  
   -   <span data-ttu-id="962b6-114">默认设置：\<属性名称 ="UseEncryption"\>0\</Property\></span><span class="sxs-lookup"><span data-stu-id="962b6-114">Default Setting: \<Property Name="UseEncryption"\>0\</Property\></span></span>  
  
   -   <span data-ttu-id="962b6-115">新的设置：\<属性名称 ="UseEncryption"\>1\</Property\></span><span class="sxs-lookup"><span data-stu-id="962b6-115">New Setting: \<Property Name="UseEncryption"\>1\</Property\></span></span>  
  
6. <span data-ttu-id="962b6-116">通过键入更新 BAM 配置**bm 更新-config-FileName:\<配置文件\>**。</span><span class="sxs-lookup"><span data-stu-id="962b6-116">Update the BAM configuration by typing **bm update-config -FileName:\<config file\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="962b6-117">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="962b6-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="962b6-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="962b6-118">See Also</span></span>  
 [<span data-ttu-id="962b6-119">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="962b6-119">BAM Management Utility</span></span>](../core/bam-management-utility.md)