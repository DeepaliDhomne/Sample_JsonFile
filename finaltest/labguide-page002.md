<inline-video source="https://www.youtube.com/embed/rfObCuGLSek" width="auto" height="auto" />
yes
```C++
public void Post([FromBody] SBModel.PartnerProfile profile)
{
    this.log.InfoFormat("Inside partner controller, attempting to add partner profile");
    PartnerManager.Instance.CreatePartner(profile, this.CurrentLoginUserEmail);
    this.log.InfoFormat("Inside partner controller, successfully added partner profile with URL:{0}", profile.PartnerUrl);
}```