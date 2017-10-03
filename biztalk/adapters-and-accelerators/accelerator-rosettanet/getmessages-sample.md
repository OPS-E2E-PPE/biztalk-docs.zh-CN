---
title: "GetMessages 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e575fa-d68b-4975-84b8-da4f17bd2db3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2ebc4ce5b87a0b698f0295fdf29c8f7138efed7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getmessages-sample"></a>GetMessages 示例
本主题提供的示例代码可以用于从一个消息不可否认性表或一个业务线 (LOB) 表中检索可读格式的消息。 消息不可否认性表包括 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]Archive 数据库中的 MessageStorageIn 和 MessageStorageOut；LOB 表包括 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA 数据库中的 MessageFromLOB 和 MessageToLOB。  
  
 将 `GetMessages` 用于故障排除或开发。 默认情况下，代码返回一个 base 64 字符串。  
  
> [!NOTE]
>  GetMessages.cs 示例代码包含两段代码，一段用于从  LOB 表中检索消息，另一段用于从不可否认性表中检索消息。 请为每种用途创建单独的应用程序。  
  
### <a name="to-retrieve-messages-from-an-lob-table"></a>从 LOB 表中检索消息  
  
1.  向您的程序中添加以下示例代码：  
  
     `private static string GetLOBMessage(string sMessageSource, string sMessageID)`  
  
2.  将 `sMessageSource` 参数设置为 MessagesFromLOB 或 MessagesToLOB 表。  
  
3.  设置`sMessageID`参数的值**MessageID**数据库中的字段。  
  
    > [!NOTE]
    >  应用程序将返回包含所检索的消息的字符串。  
  
### <a name="to-retrieve-messages-from-a-non-repudiation-table"></a>从不可否认性表中检索消息  
  
1.  向您的程序中添加以下示例代码：  
  
     `private static string GetNRMessage(string sMessageSource, string sMessageID)`  
  
2.  将 `sMessageSource` 参数设置为 MessageStorageIn 或 MessageStorageOut 表。  
  
3.  设置`sMessageID`参数的值**RecordID**数据库中的字段。  
  
    > [!NOTE]
    >  应用程序将返回包含所检索的消息的字符串。  
  
## <a name="demonstrates"></a>演示  
 GetMessages 示例包括以下两部分代码：  
  
-   一部分代码向您展示如何从一个不可否认性表中检索二进制格式的消息，并将其转换为可读的 ASCII 格式。  
  
-   另一部分代码向您展示如何从一个 LOB 表中检索消息。 由于 LOB 表中的消息已经是 ASCII 格式，因此这是一个 SQL select 语句。  
  
    > [!IMPORTANT]
    >  出于演示目的，所提供的示例代码直接使用了 SQL 语句，而这可能会导致 SQL 注入漏洞。 在生产环境下，建议使用参数化的 SQL 存储过程，而不要直接使用 SQL 语句，以防止出现这种漏洞。  
  
## <a name="example"></a>示例  
 使用以下代码示例两部分中的任何一部分，从一个不可否认性表或一个 LOB 表中检索消息。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [消息传送示例](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)