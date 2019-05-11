---
title: EXECQUERY 语句示例 mySAP 适配器在 BizTalk 中的 |Microsoft Docs
description: EXECQUERY 示例和示例使用 mySAP 适配器在 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4139af16-7c38-4ea2-b3e5-5acf8fc1f3c4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 631780b540d37e80c9218fc03f58b628e6d6e7d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373476"
---
# <a name="examples-for-execquery-statement"></a>EXECQUERY 语句示例
本主题提供了示例 EXECQUERY 语句。  


## <a name="sample-statements"></a>示例语句
-   若要执行的查询，采用 P1 和 P2 两个参数的命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
-   若要执行的查询采用参数 P1 的值的范围中的命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   若要执行的查询，采用特定的范围之外的参数 P1 的值的命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   若要执行的查询，可以采用参数 P1 的两个值之一的命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262', @P1 = '0000003263'  
    ```  
  
-   若要执行的查询，不能采用参数的特定值的命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 = '0000003262', NOT @P2 = '0000003263'  
    ```  
  
     在此示例中，P1 可以具有"0000003262"以外的任何值。 同样，P2 可以具有"0000003263"以外的任何值。  
  
-   要执行具有变体在 SAP 系统中定义的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant = ‘variant1’  
    ```  
  
     变体是指已保存的一组选择条件可以执行 SAP 查询时指定的。 例如，变体可用于指定查询的默认值。 对于具有定义的所有参数的变量的查询，不需要命令文本中指定的参数。  
  
-   若要执行的查询，不需要参数的命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'some_dummy_value'  
    ```  
  
     对于不采用参数的查询，必须指定参数，使用虚拟值。  
  
-   要执行包含的参数应为日期值的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '20080606'  
    ```  
  
     对于采用参数应为日期值的查询，必须指定日期，为 YYYYMMDD。  
  
-   若要通过指定参数的 null 值执行查询的命令。  
  
     对于此类查询，不能指定为查询：  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'null'  
    ```  
  
     相反，如果您不想要指定一个值，不应指定 P1 根本。  
  
-   要执行包含需要值大于一定数量的参数的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 > '0000003262'  
    ```  
  
-   要执行包含需要值的参数的查询命令小于一定数量。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 < '0000003262'  
    ```  
  
-   要执行包含需要值大于或等于一定数量的参数的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 >= '0000003262'  
    ```  
  
-   要执行包含需要值较小或等于一定数量的参数的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 <= '0000003262'  
    ```  
  
-   要执行包含需要值不等于一定数量的参数的查询命令。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 != '0000003262'  
    ```  
  