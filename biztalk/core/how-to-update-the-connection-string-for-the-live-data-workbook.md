---
title: 如何更新实时数据工作簿的连接字符串 |Microsoft Docs
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
ms.openlocfilehash: 2813b4ce0f448c25d75e69b1001ca006608d5993
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383630"
---
# <a name="how-to-update-the-connection-string-for-the-live-data-workbook"></a><span data-ttu-id="975fb-102">如何更新实时数据工作簿的连接字符串</span><span class="sxs-lookup"><span data-stu-id="975fb-102">How to Update the Connection String for the Live Data Workbook</span></span>
<span data-ttu-id="975fb-103">当 BAM 主导入数据库移到另一台服务器时，必须更新 BAM 实时数据工作簿中的连接字符串以指向新的服务器。</span><span class="sxs-lookup"><span data-stu-id="975fb-103">When you move the BAM Primary Import database to another server, the connection string in a BAM live data workbook must be updated to point to the new server.</span></span> <span data-ttu-id="975fb-104">您使用 BAM 外接程序 excel 进行此更新。</span><span class="sxs-lookup"><span data-stu-id="975fb-104">You use the BAM Add-in for Excel to make this update.</span></span>  
  
### <a name="to-update-the-live-data-workbook-to-point-to-a-new-server"></a><span data-ttu-id="975fb-105">若要更新实时数据工作簿，以指向新的服务器</span><span class="sxs-lookup"><span data-stu-id="975fb-105">To update the live data workbook to point to a new server</span></span>  
  
1.  <span data-ttu-id="975fb-106">单击**启动**，依次指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office Excel**。</span><span class="sxs-lookup"><span data-stu-id="975fb-106">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="975fb-107">单击**文件**菜单，并单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="975fb-107">Click the **File** menu, and then click **Open**.</span></span> <span data-ttu-id="975fb-108">导航到 BAM 实时的数据工作簿，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="975fb-108">Navigate to your BAM lived data workbook and click **Open**.</span></span>  
  
3.  <span data-ttu-id="975fb-109">单击**BAM**中的菜单**外接程序**选项卡，然后依次**BAM 数据库连接**以打开**选择 BAM 数据库**对话框。</span><span class="sxs-lookup"><span data-stu-id="975fb-109">Click the **BAM** menu in the **Add-Ins** tab, and then click **BAM DB Connection** to open the **Select BAM Database** dialog box.</span></span>  
  
4.  <span data-ttu-id="975fb-110">在中**SQL Server**文本框中，键入在其 BAM 主导入数据库当前的 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="975fb-110">In the **SQL Server** text box, type the name of the SQL server on which the BAM Primary Import database now resides.</span></span>  
  
5.  <span data-ttu-id="975fb-111">选择从 BAM 主导入数据库**数据库名称**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="975fb-111">Select the BAM Primary Import database from the **Database Name** drop-down list.</span></span>  
  
6.  <span data-ttu-id="975fb-112">单击 **“确定”** 关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="975fb-112">Click **OK** to close the dialog box.</span></span>  
  
7.  <span data-ttu-id="975fb-113">保存该工作簿。</span><span class="sxs-lookup"><span data-stu-id="975fb-113">Save the workbook.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="975fb-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="975fb-114">See Also</span></span>  
 <span data-ttu-id="975fb-115">[管理 BAM](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="975fb-115">[Managing BAM](../core/managing-bam.md) </span></span>  
 [<span data-ttu-id="975fb-116">用于 Excel 的 BAM 外接程序的使用要求</span><span class="sxs-lookup"><span data-stu-id="975fb-116">Requirements for Using the BAM Add-In for Excel</span></span>](../core/requirements-for-using-the-bam-add-in-for-excel.md)