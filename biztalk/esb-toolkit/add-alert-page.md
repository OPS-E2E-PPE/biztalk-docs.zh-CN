---
title: 添加警报页 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0023ee8d-a0d1-4257-95c6-38c95060bd62
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa93a777481c905dbedfffe5e7675335c4aec40b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290421"
---
# <a name="add-alert-page"></a>“添加警报”页
图 1 显示你可以在其中创建新的警报，门户将引发当匹配警报中指定的条件 （条件） 的错误消息到达门户的添加警报页。  
  
 ![添加警报页](../esb-toolkit/media/ch8-addalertpage.gif "Ch8 AddAlertPage")  
  
 **图 1**  
  
 **ESB 管理门户添加警报页**  
  
 在添加警报页可以执行以下操作：  
  
-   键入新警报中的名称**输入警报名称**文本框。  
  
-   指定警报中的传入异常中的字段的值的匹配方式**添加此警报的条件**的此页的部分。 从异常架构选择一个字段 (如**应用程序，错误类型**或**故障严重性)** 中**条件**下拉列表; 选择比较类型 （例如如 =、 **！ =、 > =、 < =、** 或**如**) 中**运算符**下拉列表; 并键入或选择第三个列表中的值。 当你选择的异常字段中，**值**控件更改到文本框中或供你输入或选择一个匹配值的下拉列表。  
  
-   选择或输入的条件值后, 单击**添加**链接到的列表中添加此条件**条件**页和重复添加任何更多条件，你需要为此警报的部分.  
  
-   单击**保存**按钮以名称和你指定的条件创建新的警报。