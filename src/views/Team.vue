<template>
  <v-container>
    <h1 class="text-center">The Drum Bois</h1>
    <v-row align="stretch" justify="center"
      ><!--Align=stretch makes all the columns the same size-->

      <v-col
        v-for="(person, index) in people"
        :key="index"
        class="d-flex justify-space-around"
        xs="12"
        md="6"
        lg="3"
      >
        <Profile
          :name="person.name"
          :major-grad-year="person.major"
          :bio="person.bio"
          :image-name="person.picture"
          :hometown="person.hometown"
          :linkedin="person.linkedin"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import Profile from '../components/Profile'
export default {
  components: {
    Profile
  },
  metaInfo: {
    title: 'Student Team'
  },
  data: () => ({
    people: [
      {
        name: 'Michael Disch',
        major: "Electrical Engineering '21",
        bio:
          '  "Wait, there\'s a due date?" If it weren\'t for Michael, the Drum Bois would be lost, forsaken, distraught, you name it. As our project lead, he ensured we all kept on track by guiding the ideas and direction of the project, eloquently writing our reports with exquisite prose, and always making sure we met our deadlines. After graduation, he plans to work in the DSP, Computer Architecture, and/or Animation industries.',
        picture: 'MD_Headshot.jpg',
        hometown: 'Woodbridge, VA',
        linkedin: 'https://www.linkedin.com/in/john-disch/'
      },
      {
        name: 'Matt Lichtinger',
        major: "Computer Engineering '22",
        bio:
          "   A native Ohioan, Matt's upbringing in the rival state isn't the only thing the Drum Bois have brought into question. Nervous that he could switch to the Dark Side and become a full-on Computer Scientist, they've kept an eye on this Computer Engineer. Yet, it seems they may too have been enamored by the power of darkness, as they let him use his sneaky software skills to develop our website. After graduation, he hopes to work in the tech industry.",
        picture: 'ML_Headshot.jpeg',
        hometown: 'Findlay, OH',
        linkedin: 'https://www.linkedin.com/in/mattlichtinger/'
      },
      {
        name: 'Devon Davis',
        major: "Electrical Engineering '21",
        bio:
          '  "Nick, I am your father". When the world needed him most, our code abstraction lord came to the rescue. Whether it be writing his own functions or making sure they all work together for one big, beautiful analysis, Devon has been our MATLAB messiah, embracing Nick\'s fervor and directing it toward greatness. The only native of Michigan, he makes sure to give us a lesson on the mitten\'s geography every meeting. After graduation, he plans to work in the power systems industry.',
        picture: 'DD_Headshot.png',
        hometown: 'Muir, MI',
        linkedin: 'https://www.linkedin.com/in/devon-davis-609929151/'
      },
      {
        name: 'Nick Cahill',
        major: "Electrical Engineering '22",
        bio:
          '   Some call him the MATLAB prodigy, others say he is secretly the founder of MathWorks, but we just like to call him "Dat Boi". A DSP whiz and our lead function coder, Nick has puzzled his way through even the crispiest of conundrums for our algorithms. After graduation, he plans to work in the aerospace or semiconductor industries.',
        picture: 'NC_Headshot.png',
        hometown: 'New York City, NY',
        linkedin: 'https://www.linkedin.com/in/nicholas-cahill-a280a617a/'
      }
    ]
  })
}
</script>
