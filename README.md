# Mission model hot update example

1. `./gradlew assemble`
2. `docker compose up -d` - this will mount your ./build/libs directory as the aerie_file_store
3. Upload a mission model. After doing this, check your ./build/libs folder - there should be a new jar file in there with gibberish appended to the name
4. Run `python rename_model.py` - this will have Aerie use your missionmodel.jar instead of the one with gibberish in it
5. Make a new plan, upload your view, simulate, make sure that's all working
6. Edit refresh_model.py to refer to the correct model id
7. Try making a change to your mission model
8. Whenever you recompile your model, do the following:
```
./gradlew assemble && python refresh_model.py
```
