---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php


$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);


$graphServiceClient->bookingBusinesses()->byBookingBusinessId('bookingBusiness-id')->customQuestions()->byBookingCustomQuestionId('bookingCustomQuestion-id')->delete()->wait();

```