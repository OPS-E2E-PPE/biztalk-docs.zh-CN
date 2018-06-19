---
title: 如何更新实时数据工作簿的连接字符串 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d2702fb-637c-46db-8b62-08ae15f983ba
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60de5d1ae904bdefffcf490e3a39d000b28a341d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255309"
---
# <a name="how-to-update-the-connection-string-for-the-live-data-workbook"></a><span data-ttu-id="2d16b-102">如何更新实时数据工作簿的连接字符串</span><span class="sxs-lookup"><span data-stu-id="2d16b-102">How to Update the Connection String for the Live Data Workbook</span></span>
<span data-ttu-id="2d16b-103">BAM 主导入数据库移动到另一个服务器时，必须更新 BAM 实时数据工作簿中的连接字符串以指向新的服务器。</span><span class="sxs-lookup"><span data-stu-id="2d16b-103">When you move the BAM Primary Import database to another server, the connection string in a BAM live data workbook must be updated to point to the new server.</span></span> <span data-ttu-id="2d16b-104">你使用 BAM add-in for Excel 进行此更新。</span><span class="sxs-lookup"><span data-stu-id="2d16b-104">You use the BAM Add-in for Excel to make this update.</span></span>  
  
### <a name="to-update-the-live-data-workbook-to-point-to-a-new-server"></a><span data-ttu-id="2d16b-105">若要更新实时数据工作簿，以指向新的服务器</span><span class="sxs-lookup"><span data-stu-id="2d16b-105">To update the live data workbook to point to a new server</span></span>  
  
1.  <span data-ttu-id="2d16b-106">单击**启动**，指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office Excel**。</span><span class="sxs-lookup"><span data-stu-id="2d16b-106">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="2d16b-107">单击**文件**菜单，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="2d16b-107">Click the **File** menu, and then click **Open**.</span></span> <span data-ttu-id="2d16b-108">导航到你 BAM 生存期的数据的工作簿并单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="2d16b-108">Navigate to your BAM lived data workbook and click **Open**.</span></span>  
  
3.  <span data-ttu-id="2d16b-109">单击**BAM**菜单中的**外接程序**选项卡上，并依次**BAM 数据库连接**以打开**选择 BAM 数据库**对话框。</span><span class="sxs-lookup"><span data-stu-id="2d16b-109">Click the **BAM** menu in the **Add-Ins** tab, and then click **BAM DB Connection** to open the **Select BAM Database** dialog box.</span></span>  
  
4.  <span data-ttu-id="2d16b-110">在**SQL Server**文本框中，键入驻留在其上 BAM 主导入数据库现在的 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="2d16b-110">In the **SQL Server** text box, type the name of the SQL server on which the BAM Primary Import database now resides.</span></span>  
  
5.  <span data-ttu-id="2d16b-111">选择从 BAM 主导入数据库**数据库名称**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="2d16b-111">Select the BAM Primary Import database from the **Database Name** drop-down list.</span></span>  
  
6.  <span data-ttu-id="2d16b-112">单击 **“确定”** 关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="2d16b-112">Click **OK** to close the dialog box.</span></span>  
  
7.  <span data-ttu-id="2d16b-113">保存该工作簿。</span><span class="sxs-lookup"><span data-stu-id="2d16b-113">Save the workbook.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d16b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d16b-114">See Also</span></span>  
 <span data-ttu-id="2d16b-115">[管理 BAM](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="2d16b-115">[Managing BAM](../core/managing-bam.md) </span></span>  
 [<span data-ttu-id="2d16b-116">使用 for Excel 的 BAM 外接程序的要求</span><span class="sxs-lookup"><span data-stu-id="2d16b-116">Requirements for Using the BAM Add-In for Excel</span></span>](../core/requirements-for-using-the-bam-add-in-for-excel.md)