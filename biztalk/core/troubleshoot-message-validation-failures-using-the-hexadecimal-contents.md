---
title: 通过查看挂起的消息的十六进制内容来解决消息验证失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf14cd9-2d4b-43a3-9738-52bfd879e1e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 562caf377691e8bfcea5d05bba307e28859d7999
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243119"
---
# <a name="troubleshooting-message-validation-failures-by-viewing-the-hexadecimal-contents-of-suspended-messages"></a>通过查看挂起的消息的十六进制内容来解决消息验证失败
如果消息由于验证失败而挂起，可能会有助于查看来确定验证失败的原因的消息部分的十六进制表示形式。 本主题列出了可后接若要查看的十六进制表示形式的挂起的消息部分的步骤。  
  
## <a name="use-the-message-details-dialog-box-to-view-message-parts"></a>使用消息详细信息对话框中查看消息部分  
 请按照下列步骤查看消息部分的十六进制表示形式：  
  
1.  使用**查询**在 BizTalk 管理控制台中返回的结果集与一个或多个挂起的消息的选项卡。 请参阅[如何搜索消息](../core/how-to-search-for-messages.md)有关详细信息。  
  
2.  双击你想要进行调查以显示对挂起的消息**消息的详细信息**消息对话框。  
  
3.  单击左侧窗格中的消息部分**消息的详细信息**对话框以显示消息部分。  
  
    > [!NOTE]
    >  消息可能具有 0、 1 或多个消息部分。 大部分消息通常只有一个消息部分，称作"正文"。  
  
4.  单击**二进制**的右窗格中的选项卡**消息的详细信息**对话框以显示消息部分的十六进制表示形式。  
  
5.  检查以下的消息部分中的字符的十六进制表示形式：  
  
    -   缺失或无效字节顺序标记。 有关字节顺序标记请参阅[ http://go.microsoft.com/fwlink/?LinkId=196380 ](http://go.microsoft.com/fwlink/?LinkId=196380)。  
  
    -   Unix 和 Windows 中的换行符编码之间的差异。 Unix 使用十六进制换行符 (0A) 指示换行，Windows 使用十六进制回车符 (0d) 和换行符 (0A) 指示换行。  
  
    -   消息部分中有无效控制字符。 不显示在文本视图中的消息部分中的控制字符可能会看到在二进制视图中。  
  
    -   无效空字符消息部分可能会导致消息部分被截断。 空字符表示为十六进制值 (00)。  
  
    -   无效的字符偏移量位置平面文件中。 显示消息部分，若要查看位置平面文件中的数据的偏移量的十六进制表示形式。  
  
## <a name="see-also"></a>请参阅  
 [调查业务流程、端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)