---
title: GetMessages 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29e575fa-d68b-4975-84b8-da4f17bd2db3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb1c30fa6b90ba0e9e523a54b24030dd32b8ff80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283659"
---
# <a name="getmessages-sample"></a>GetMessages 示例
本主题提供了可用于从消息不可否认性表之一或以可读形式的业务线 (LOB) 表之一检索消息的示例代码。 消息不可否认性表包括 MessageStorageIn 和 MessageStorageOut 中的[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]存档数据库; LOB 表包括的 MessageFromLOB 和 MessageToLOB 中的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据数据库。  
  
 使用`GetMessages`进行故障排除或开发。 默认情况下，代码返回 base 64 字符串。  
  
> [!NOTE]
>  GetMessages.cs 示例代码包含两个部分的代码 — 一个用于从一个 LOB 表中检索消息，另一个用于从不可否认性表之一检索消息。 为每种用途创建单独的应用程序。  
  
### <a name="to-retrieve-messages-from-an-lob-table"></a>若要从 LOB 表中检索消息  
  
1.  将下面的示例代码添加到您的程序：  
  
     `private static string GetLOBMessage(string sMessageSource, string sMessageID)`  
  
2.  设置`sMessageSource`MessagesFromLOB 或 MessagesToLOB 表参数。  
  
3.  设置`sMessageID`的值的参数**MessageID**数据库中的字段。  
  
    > [!NOTE]
    >  应用程序返回一个字符串，包含检索到的消息。  
  
### <a name="to-retrieve-messages-from-a-non-repudiation-table"></a>若要从不可否认性表中检索消息  
  
1.  将下面的示例代码添加到您的程序：  
  
     `private static string GetNRMessage(string sMessageSource, string sMessageID)`  
  
2.  设置`sMessageSource`MessageStorageIn 或 MessageStorageOut 表参数。  
  
3.  设置`sMessageID`的值的参数**RecordID**数据库中的字段。  
  
    > [!NOTE]
    >  应用程序返回一个字符串，包含检索到的消息。  
  
## <a name="demonstrates"></a>演示  
 GetMessages 示例包括以下两个部分的代码：  
  
-   一个部分演示如何从不可否认性表之一检索二进制消息，并将其转换为可读 ASCII 格式。  
  
-   其他部分演示如何从一个 LOB 表中检索一条消息。 由于 LOB 表中的消息已在 ASCII 格式，这是 SQL select 语句。  
  
    > [!IMPORTANT]
    >  出于演示目的，提供的示例代码使用很容易导致 SQL 注入漏洞的直接 SQL 语句。 在生产环境中，建议你使用参数化的 SQL 存储过程，而不是直接使用 SQL 语句，以防止出现此类漏洞。  
  
## <a name="example"></a>示例  
 使用下面的代码示例中的两个部分之一从不可否认性表中的一个或一个 LOB 表中检索消息。  
  
```  
using System;  
using System.Text;  
using System.Data.SqlClient;   
using Microsoft.Solutions.BTARN.Shared;  
  
namespace Microsoft.Solutions.BTARN.Admin  
{  
  
      /// <summary>  
      /// Summary description for GetMessages.  
      /// </summary>  
      class GetMessages  
      {  
            /// <summary>  
            /// The main entry point for the application.  
            /// </summary>  
            [STAThread]  
            static void Main(string[] args)  
            {  
                  Console.WriteLine(GetLOBMessage("MessagesFromLOB", "bce5b580daf543a990a4f37331f31e42"));  
                  Console.WriteLine(GetLOBMessage("MessagesToLOB", "bce5b580daf543a990a4f37331f31e42"));  
                  Console.WriteLine(GetNRMessage("MessageStorageIn", "dc06e9cfecd746a889dd6ea7beb3ba21"));  
                  Console.WriteLine(GetNRMessage("MessageStorageOut", "dc06e9cfecd746a889dd6ea7beb3ba21"));  
            }  
  
            /// <summary>  
            /// Retrieve a message from the LOB tables in the BTARNDATA database  
            /// </summary>  
            /// <param name="sMessageSource">Can be either MessagesFromLOB or MessagesToLOB</param>  
            /// <param name="sMessageID">The value of the MessageID field in the database</param>  
            /// <returns>Returns a string that contains the retrieved message</returns>        
            private static string GetLOBMessage(string sMessageSource, string sMessageID)  
            {  
                  SqlDataReader localReader = null;  
                  SqlConnection sqlConnection = null;  
                  SqlCommand sqlCommand = null;  
                  string sReturnedMessage="";              
                  string sQuery;  
  
                  sqlConnection = new SqlConnection(RuntimeGlobal.DataDbConnectionString);  
                  sQuery = "SELECT ServiceContent from " + sMessageSource + " WHERE MessageID=N'" + sMessageID +"'";  
  
                  sqlCommand = new SqlCommand(sQuery, sqlConnection);  
                  sqlConnection.Open();  
  
                  localReader = sqlCommand.ExecuteReader();  
  
                  if (localReader.Read())  
                        sReturnedMessage=localReader.GetString(0);  
  
                  localReader.Close();  
                  sqlConnection.Close();        
                  return sReturnedMessage;              
            }  
  
            /// <summary>  
            /// Retrieve a message from the non-repudiation tables in the BTARNArchive database  
            /// </summary>  
            /// <param name="sMessageSource">Can be either MessageStorageIn or MessageStorageOut</param>  
            /// <param name="sMessageID">The value of the RecordID field in the database</param>  
            /// <returns>Returns a string that contains the retrieved message</returns>  
            private static string GetNRMessage(string sMessageSource, string sMessageID)  
            {  
                  SqlDataReader localReader = null;  
                  SqlConnection sqlConnection = null;  
                  SqlCommand sqlCommand = null;  
                  string sReturnedMessage="";              
                  string sQuery;  
  
                  sqlConnection = new SqlConnection(RuntimeGlobal.ArchiveDbConnectionString);  
                  sQuery = "SELECT Content from " + sMessageSource + " WHERE RecordID=N'" + sMessageID +"'";  
  
                  sqlCommand = new SqlCommand(sQuery, sqlConnection);  
                  sqlConnection.Open();  
  
                  localReader = sqlCommand.ExecuteReader();  
  
                  if (localReader.Read())  
                  {  
                        //Determine the size of the field in bytes and create a new byte array  
                        byte[] bData= new byte[localReader.GetBytes(0, 0, null, 0, 0)];  
  
                        //Read the value of the field into bData  
                        localReader.GetBytes(0, 0, bData, 0, bData.Length);  
  
                        //Convert the byte array into a string  
                        sReturnedMessage=Encoding.ASCII.GetString(bData);  
                  }  
  
                  localReader.Close();  
                  sqlConnection.Close();        
                  return sReturnedMessage;              
            }  
      }  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [消息传送示例](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)