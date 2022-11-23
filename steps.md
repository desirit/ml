Prerequisite: 
* PIP3
  - Install using `sudo apt-get install python3-pip`
- Step1: Run "pip3 install transformers==4.6.1"
- step2: RUN "pip3 install torch==1.9.0"
- Step3: RUN "python3 summarization.py"
- Step4: docker build -t summarization .
- Step5: docker run -p 80:80 --gpus all summarization


To test: 
http://{publicIP}/ 

That should display a message "This worked !!"

To do the actual summarization: 
- Use Postman tool
- send a POST request: http://{publicIP}/summary

where header --> `Content-Type` = `application/json`
in the body secion: 
- select `raw` and submit a JSON blob: 

example: 
```
{
    "text": "Kathryn Dwyer Sullivan (born October 3, 1951) is an American geologist and oceanographer, and a former NASA astronaut and US Navy officer. She was a crew member on three Space Shuttle missions. A graduate of University of California, Santa Cruz in the United States, and Dalhousie University in Nova Scotia, Canada—where she earned a Doctor of Philosophy degree in geology in 1978—Sullivan was selected as one of the six women among the 35 astronaut candidate in NASA Astronaut Group 8, the first group to include women. During her training, she became the first woman to be certified to wear a United States Air Force pressure suit, and on July 1, 1979, she set an unofficial sustained American aviation altitude record for women. During her first mission, STS-41-G, Sullivan performed the first extra-vehicular activity (EVA) by an American woman. On her second, STS-31, she helped deploy the Hubble Space Telescope. On the third, STS-45, she served as Payload Commander on the first Spacelab mission dedicated to NASA's Mission to Planet Earth. Sullivan was Under Secretary of Commerce for Oceans and Atmosphere and Administrator of the National Oceanic and Atmospheric Administration (NOAA) after being confirmed by the US Senate on March 6, 2014. Her tenure ended on January 20, 2017, after which she was designated as the 2017 Charles A. Lindbergh Chair of Aerospace History at the Smithsonian Institution's National Air and Space Museum, and also served as a Senior Fellow at the Potomac Institute for Policy Studies. On June 7, 2020, Sullivan became the first woman to dive to the Challenger Deep in the Mariana Trench, the deepest part of the Earth's oceans. In September 2021 President Joe Biden appointed her to the President's Council of Advisors on Science and Technology.",
    "min_length": 75,
    "max_length": 150
}
```

GPU used: g4dn.4xlarge
<br>
AMI: Deep Learning AMI GPU PyTorch 1.13.0 (Ubuntu 20.04) 20221110
