---
title: 创建 QRY^Q01.txt 文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ac96587-264f-4743-a90b-4763d330e320
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b3bc9de81259ba71547e3fb887e91872e9e549c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960163"
---
# <a name="create-the-qryq01txt-file"></a><span data-ttu-id="f4791-102">创建 QRY^Q01.txt 文件</span><span class="sxs-lookup"><span data-stu-id="f4791-102">Create the QRY^Q01.txt File</span></span>
<span data-ttu-id="f4791-103">使用以下过程创建患者查询 QRY^Q01.txt 消息文件。</span><span class="sxs-lookup"><span data-stu-id="f4791-103">Use the following procedure to create the patient query QRY^Q01.txt message file.</span></span> <span data-ttu-id="f4791-104">你将更高版本使用此文件来验证教程的方案。</span><span class="sxs-lookup"><span data-stu-id="f4791-104">You will use this file later to verify the tutorial scenario.</span></span>  
  
### <a name="to-create-the-qryq01txt-file"></a><span data-ttu-id="f4791-105">若要创建 QRY^Q01.txt 文件</span><span class="sxs-lookup"><span data-stu-id="f4791-105">To create the QRY^Q01.txt file</span></span>  
  
1.  <span data-ttu-id="f4791-106">打开编辑器，如记事本，并将以下文本复制到编辑器：</span><span class="sxs-lookup"><span data-stu-id="f4791-106">Open an editor, such as Notepad, and copy the following text into the editor:</span></span>  
  
    ```  
    MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
    QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
    ```  
  
2.  <span data-ttu-id="f4791-107">将文件另存**QRY^Q01.txt**中\<*驱动器*:\>files\microsoft BizTalk\<版本\>HL7\SDK\ 快捷键Interrogative 的教程文件夹，然后关闭编辑器。</span><span class="sxs-lookup"><span data-stu-id="f4791-107">Save the file as **QRY^Q01.txt** in the \<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder, and then close the editor.</span></span>  
  
 <span data-ttu-id="f4791-108">继续执行[创建 DSR.txt 文件](../../adapters-and-accelerators/accelerator-hl7/create-the-dsr-txt-file.md)。</span><span class="sxs-lookup"><span data-stu-id="f4791-108">Proceed to [Create the DSR.txt File](../../adapters-and-accelerators/accelerator-hl7/create-the-dsr-txt-file.md).</span></span>