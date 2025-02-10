```C++
 public ActionResult GetLabGuideQuestionsByVoucherCodeAndPageNumber(string voucherCode, int pageNumber)
 {
     _logger.LogWarning($"LabGuideController.GetLabGuideQuestionsByVoucherCodeAndPageNumber - Questions/{voucherCode}/{pageNumber} : Called");

     var questions = _labGuideService.GetLabGuideQuestionsByVoucherCodeAndPageNumber(voucherCode, pageNumber);

     if (questions == null)
     {
         return NotFound();
     }

     var response = System.Text.Json.JsonSerializer.Serialize(questions, new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase });

     _logger.LogWarning($"LabGuideController.GetLabGuideQuestionsByVoucherCodeAndPageNumber - Questions/{voucherCode}/{pageNumber} : End");

     return Content(response);
 }
 ```